<!-- ================= HEADER ================= -->

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=venom&height=250&color=0:0f2027,50:203a43,100:61DAFB&text=React%20Internals%20Deep%20Dive&fontSize=40&fontColor=ffffff&animation=fadeIn&fontAlignY=38"/>
</p>

<h1 align="center">⚛️ React Internals – Architecture & Rendering Deep Dive</h1>

<p align="center">
  Fiber Architecture • Rendering Lifecycle • Concurrent React • Hooks Flow • Strict Mode
</p>

---

# 📚 Table of Contents

1. Fiber Architecture  
2. React Rendering Lifecycle (Diagram)  
3. Concurrent React Deep Dive  
4. Hook Execution Flow  
5. Strict Mode & Automatic Batching  

---

# 🧠 1. Fiber Architecture Explained

## Why Fiber Was Introduced?

Before React 16:
- Stack Reconciler
- Rendering was synchronous
- Large UI updates could block the main thread

React 16 introduced **Fiber Architecture**.

---

## 🔹 What is Fiber?

Fiber is a reimplementation of React's reconciliation algorithm.

It allows:
- Incremental rendering
- Priority-based updates
- Pausing and resuming work
- Better scheduling

---

## 🔹 Core Concepts of Fiber

### 1️⃣ Fiber Node

Each component becomes a Fiber node.

A fiber node contains:
- type (component type)
- stateNode (DOM or class instance)
- child
- sibling
- return (parent)
- pendingProps
- memoizedProps
- memoizedState

---

### 2️⃣ Two Phases of Fiber

React work happens in two phases:

## 🟡 Render Phase (Reconciliation Phase)

- Builds new Fiber tree
- Can be paused
- Can be aborted
- Pure computation
- No DOM updates

## 🟢 Commit Phase

- Applies changes to DOM
- Runs useEffect
- Cannot be interrupted

---

## 🔹 Fiber Tree Structure

React keeps two trees:

```
Current Tree (Displayed UI)
Work-In-Progress Tree (Building)
```

After render phase finishes:

```
WIP Tree becomes Current Tree
```

This process is called:
👉 Double Buffering

---

# 🔄 2. React Rendering Lifecycle (Functional Components)

Here is the modern lifecycle flow:

```
Initial Render
   ↓
Render Phase (Pure)
   ↓
Reconciliation (Diffing)
   ↓
Commit Phase
   ↓
DOM Updated
   ↓
useLayoutEffect runs
   ↓
Browser Paint
   ↓
useEffect runs
```

---

## 🔹 On State Update

```
setState()
   ↓
Schedule Update
   ↓
Render Phase
   ↓
Diff Old vs New Virtual DOM
   ↓
Commit Phase
   ↓
Cleanup previous effects
   ↓
Run new effects
```

---

## 🔹 Effect Execution Order

```
Render
Commit DOM
useLayoutEffect
Paint
useEffect
```

---

# 🚀 3. Concurrent React Deep Dive

Introduced in React 18.

Concurrent React allows:
- Interruptible rendering
- Priority-based scheduling
- Smoother UI updates

---

## 🔹 What Problem Does It Solve?

Example:

- User typing in input
- Large list rendering
- UI becomes laggy

Concurrent React allows:
- Urgent updates first
- Non-urgent updates later

---

## 🔹 Key Features

### 1️⃣ useTransition

```js
const [isPending, startTransition] = useTransition();

startTransition(() => {
  setList(filteredData);
});
```

Marks updates as non-urgent.

---

### 2️⃣ useDeferredValue

```js
const deferredValue = useDeferredValue(searchTerm);
```

Delays non-urgent updates.

---

### 3️⃣ Time Slicing

React breaks rendering work into small chunks.

Instead of:

```
Big blocking render
```

It does:

```
Small chunk → Pause → Continue
```

---

## 🔹 Priority Levels (Simplified)

- Immediate (click, input)
- User Blocking
- Normal
- Low
- Idle

React Scheduler assigns priority automatically.

---

# 🧠 4. Hook Execution Flow Visualization

Hooks rely on call order.

---

## 🔹 How React Tracks Hooks

Internally React stores hooks in a linked list.

Example:

```js
function Component() {
  useState();
  useEffect();
  useRef();
}
```

Internally stored as:

```
Hook 1 → Hook 2 → Hook 3
```

React identifies hooks by:
👉 Call order, not name.

---

## 🔹 What Happens During Re-render?

React replays hooks in the same order.

If order changes:

❌ React throws error.

---

## 🔹 Hook Flow Diagram

```
Render Start
   ↓
Call useState
   ↓
Call useEffect
   ↓
Call useRef
   ↓
Render End
   ↓
Commit
   ↓
Run Effects
```

---

## 🔹 Why Hooks Cannot Be Conditional

Wrong:

```js
if (condition) {
  useState();
}
```

Because next render order changes.

React depends on stable hook order.

---

# ⚠ 5. Strict Mode & Automatic Batching

---

## 🔹 Strict Mode (React 18)

In development mode:

React intentionally runs:

- Components twice
- useEffect twice
- State initialization twice

Why?

To detect:
- Side effects
- Unsafe operations
- Memory leaks

Important:
Strict Mode double execution happens only in development.

---

## 🔹 Automatic Batching (React 18)

Before React 18:

```js
setCount(c => c + 1);
setFlag(true);
```

Would cause:
👉 Two re-renders (if outside event handler)

After React 18:
👉 All updates inside async, promises, timeouts are batched.

Example:

```js
setTimeout(() => {
  setCount(c => c + 1);
  setFlag(true);
});
```

Now:
✔ Single re-render

---

## 🔹 Why Batching Matters?

- Better performance
- Fewer re-renders
- Smoother UI

---

# 🏗 Summary Architecture Overview

```
User Action
   ↓
Schedule Update
   ↓
Fiber Render Phase (Interruptible)
   ↓
Reconciliation
   ↓
Commit Phase (Non-interruptible)
   ↓
DOM Update
   ↓
Layout Effects
   ↓
Paint
   ↓
Passive Effects
```

---

# 💎 Final Thought

Understanding React internals gives you:

- Better debugging skills
- Performance awareness
- Cleaner architecture decisions
- Senior-level frontend knowledge

---

<p align="center">
  Built with ⚛️ by Mihir Patel  
  React Internals Explorer
</p>
