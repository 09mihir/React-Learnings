<!-- ================= HEADER ================= -->

<h1 align="center">
  ⚛️ React State & State Management – Complete Developer Notes
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/React-18+-61DAFB?style=for-the-badge&logo=react" />
  <img src="https://img.shields.io/badge/State-Management-ff6b6b?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Level-Frontend%20Architecture-success?style=for-the-badge" />
</p>

---

# 🧠 What is State in React?

> **State is a JavaScript object that stores dynamic data and determines component behavior.**

When state changes → React re-renders the component.

---

# 🔄 How React State Works (Flow Diagram)


::contentReference[oaicite:0]{index=0}


### 🔁 State Update Flow

1. User Interaction (Click / Input)
2. `setState()` or state updater runs
3. React schedules update
4. Component re-renders
5. Virtual DOM compares changes
6. Real DOM updates

> React follows **Unidirectional Data Flow**

---

# 📦 Types of State in React

| Type | Description | Example |
|------|------------|---------|
| Local State | Inside component | useState |
| Global State | Shared across app | Redux / Context |
| Server State | From backend | API Data |
| URL State | Stored in URL | React Router |
| Derived State | Computed from existing state | useMemo |

---

# 🎯 1. Local State (useState)

```js
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <>
      <h2>{count}</h2>
      <button onClick={() => setCount(prev => prev + 1)}>
        Increase
      </button>
    </>
  );
}
```

### Key Points

✔ State updates are asynchronous  
✔ Never mutate directly  
✔ Always use updater function for safe updates  

---

# 🔁 2. Managing Complex State (useReducer)

When state logic becomes complex:

```js
import { useReducer } from "react";

function reducer(state, action) {
  switch (action.type) {
    case "increment":
      return { count: state.count + 1 };
    default:
      return state;
  }
}

const [state, dispatch] = useReducer(reducer, { count: 0 });
```

Best for:
- Forms
- Multi-step workflows
- Complex UI states

---

# 🌍 3. Global State Management

## Option 1 – Context API

Used to avoid prop drilling.

```js
const ThemeContext = createContext();

function App() {
  return (
    <ThemeContext.Provider value="dark">
      <Child />
    </ThemeContext.Provider>
  );
}
```

---

## Option 2 – Redux Toolkit

Used in large applications.

```
UI → dispatch → reducer → store → UI
```

Best for:
- Large apps
- Shared dashboard state
- Complex business logic

---

# 🌐 4. Server State

Server state is different from local state.

Examples:
- API data
- Loading state
- Error state

Modern solutions:
- RTK Query
- React Query
- SWR

---

# 📊 State Architecture Comparison

| Tool | Best For | Complexity |
|------|----------|------------|
| useState | Small components | Low |
| useReducer | Complex local logic | Medium |
| Context API | Medium apps | Medium |
| Redux Toolkit | Large apps | High |
| RTK Query | API-heavy apps | Medium |

---

# 🧠 Controlled vs Uncontrolled Components

## Controlled Component

```js
const [value, setValue] = useState("");

<input 
  value={value}
  onChange={(e) => setValue(e.target.value)}
/>
```

React controls input state.

---

## Uncontrolled Component

```js
const inputRef = useRef();

<input ref={inputRef} />
```

DOM controls input.

---

# ⚡ Lifting State Up

When multiple components need same data:

```
Parent
 ├── Child A
 └── Child B
```

State lives in parent → passed via props.

---

# 🏗 State Management Strategy (Industry Level)

### 🔹 Small App
- useState
- Context if needed

### 🔹 Medium App
- useReducer
- Context API

### 🔹 Large Scale App
- Redux Toolkit
- RTK Query
- Normalized state structure

---

# 🚀 Performance Optimization in State

✔ Avoid unnecessary re-renders  
✔ Use `React.memo()`  
✔ Use `useMemo()` for expensive calculations  
✔ Use `useCallback()` for stable functions  
✔ Normalize large datasets  

---

# 🔥 Common State Mistakes

❌ Mutating state directly  
❌ Storing derived state unnecessarily  
❌ Overusing global state  
❌ Putting everything in Redux  
❌ Not handling loading/error states  

---

# 🎯 Interview Notes

- What is state?
- Difference between props & state?
- Why state updates are async?
- When to use useReducer?
- How to manage global state?
- What is lifting state up?

---

# 💎 Final Thought

> State is the heart of React applications.  
> Mastering state management = mastering React architecture.

---

<p align="center">
  Built with ⚛️ by Mihir Patel
</p>
