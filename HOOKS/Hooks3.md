<!-- ================= PREMIUM HEADER ================= -->

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=venom&height=260&color=0:0f2027,50:203a43,100:61DAFB&text=React%20Hooks%20Mastery&fontSize=42&fontColor=ffffff&animation=fadeIn&fontAlignY=38"/>
</p>

<h1 align="center">⚛️ React Hooks – Complete Developer Documentation</h1>

<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?size=22&duration=3000&color=61DAFB&center=true&vCenter=true&width=700&lines=Complete+React+Hooks+Guide;Core+to+Advanced+Concepts;All+useEffect+Variations;Industry+Level+Understanding" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/React-18+-61DAFB?style=for-the-badge&logo=react" />
  <img src="https://img.shields.io/badge/Hooks-Deep%20Dive-blueviolet?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Level-Industry%20Ready-success?style=for-the-badge" />
</p>

---

# 📚 Table of Contents

1. Introduction to Hooks  
2. Why Hooks Over Classes  
3. Rules of Hooks  
4. Core Hooks  
5. useEffect – All Variations (Complete Guide)  
6. Performance Hooks  
7. Advanced Hooks  
8. Custom Hooks  
9. Best Practices  
10. Common Mistakes  
11. Interview Preparation Notes  

---

# 🚀 1. Introduction to Hooks

React Hooks were introduced in **React 16.8** to allow functional components to:

- Use state
- Handle lifecycle logic
- Reuse component logic
- Avoid class components

Hooks make functional components powerful and scalable.

---

# 🆚 2. Why Hooks Over Classes?

| Class Components | Functional + Hooks |
|------------------|-------------------|
| Complex lifecycle methods | Clean useEffect |
| Hard to reuse logic | Custom Hooks |
| this keyword confusion | No this |
| Boilerplate heavy | Cleaner code |

Hooks promote **composition over inheritance**.

---

# 📏 3. Rules of Hooks

```js
// ✅ Correct
const [count, setCount] = useState(0);

// ❌ Wrong
if (condition) {
  useState(0);
}
```

✔ Call hooks at top level  
✔ Only inside React function components  
✔ Never inside loops or conditions  

---

# 🎯 4. Core Hooks

---

## 🔹 useState

Used for local component state.

```js
const [count, setCount] = useState(0);
```

### Key Points:
- Triggers re-render
- State updates are asynchronous
- Never mutate state directly
- Can store any type (array, object, boolean, etc.)

---

## 🔹 useContext

Used to avoid prop drilling.

```js
const theme = useContext(ThemeContext);
```

### When to Use:
- Global theme
- Authentication state
- Shared settings

---

## 🔹 useRef

```js
const inputRef = useRef(null);
```

### Uses:
- Access DOM elements
- Store mutable values
- Persist value between renders
- Does NOT trigger re-render

---

## 🔹 useReducer

Best for complex state logic.

```js
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

Used when:
- Multiple state transitions
- Complex update logic
- Large forms

---

# 🌍 5. useEffect – Complete Guide (All Variations)

useEffect handles **side effects** like:

- API calls
- Subscriptions
- Timers
- DOM manipulation
- Logging
- External system sync

---

## 🔹 Basic Syntax

```js
useEffect(() => {
  // effect logic

  return () => {
    // cleanup logic
  };
}, [dependencies]);
```

---

## 1️⃣ Runs on Every Render

```js
useEffect(() => {
  console.log("Runs every render");
});
```

No dependency array.

---

## 2️⃣ Runs Only Once (On Mount)

```js
useEffect(() => {
  console.log("Runs once after mount");
}, []);
```

Equivalent to componentDidMount.

---

## 3️⃣ Runs When Dependency Changes

```js
useEffect(() => {
  console.log("Runs when count changes");
}, [count]);
```

Equivalent to componentDidUpdate.

---

## 4️⃣ Multiple Dependencies

```js
useEffect(() => {
  console.log("Runs when count OR user changes");
}, [count, user]);
```

---

## 5️⃣ Cleanup Function

```js
useEffect(() => {
  const interval = setInterval(() => {
    console.log("Running");
  }, 1000);

  return () => clearInterval(interval);
}, []);
```

Cleanup runs:
- On unmount
- Before next effect execution

Equivalent to componentWillUnmount.

---

## 6️⃣ Conditional Logic (Correct Way)

❌ Never call hooks conditionally.

✅ Correct pattern:

```js
useEffect(() => {
  if (count > 5) {
    console.log("Count is greater than 5");
  }
}, [count]);
```

---

## 7️⃣ Fetch API Example

```js
useEffect(() => {
  async function fetchData() {
    const res = await fetch("/api/data");
    const data = await res.json();
    console.log(data);
  }

  fetchData();
}, []);
```

---

## 8️⃣ Event Listener

```js
useEffect(() => {
  const handleResize = () => {
    console.log(window.innerWidth);
  };

  window.addEventListener("resize", handleResize);

  return () => window.removeEventListener("resize", handleResize);
}, []);
```

---

## 9️⃣ Debouncing

```js
useEffect(() => {
  const timer = setTimeout(() => {
    console.log("Searching...");
  }, 500);

  return () => clearTimeout(timer);
}, [searchTerm]);
```

---

## 🔟 Skipping Initial Render

```js
const isFirst = useRef(true);

useEffect(() => {
  if (isFirst.current) {
    isFirst.current = false;
    return;
  }

  console.log("Runs after first render");
}, [value]);
```

---

## 1️⃣1️⃣ Abort Controller (Prevent Memory Leaks)

```js
useEffect(() => {
  const controller = new AbortController();

  fetch("/api/data", { signal: controller.signal });

  return () => controller.abort();
}, []);
```

---

## 1️⃣2️⃣ Derived State Effect

```js
useEffect(() => {
  setTotal(price * quantity);
}, [price, quantity]);
```

⚠ Often better to compute directly.

---

## 1️⃣3️⃣ useEffect vs useLayoutEffect

| Hook | Execution Timing |
|------|------------------|
| useEffect | After paint |
| useLayoutEffect | Before paint |

```js
useLayoutEffect(() => {
  // DOM measurement
}, []);
```

---

## ⚠ Important Notes

- Effects run after render commit phase
- Cleanup runs before next effect
- Dependencies use shallow comparison
- Strict Mode runs effects twice in development (React 18)

---

# ⚡ 6. Performance Hooks

---

## 🔹 useMemo

```js
const memoValue = useMemo(() => {
  return expensiveCalculation(data);
}, [data]);
```

Prevents unnecessary recalculation.

---

## 🔹 useCallback

```js
const memoFn = useCallback(() => {
  doSomething();
}, []);
```

Prevents function recreation.

---

# 🚀 7. Advanced Hooks

---

## 🔹 useLayoutEffect

Runs synchronously before browser paint.

---

## 🔹 useImperativeHandle

Used with forwardRef.

```js
useImperativeHandle(ref, () => ({
  focus: () => inputRef.current.focus()
}));
```

---

## 🔹 useTransition (React 18)

```js
const [isPending, startTransition] = useTransition();
```

Used for non-blocking UI updates.

---

# 🛠 8. Custom Hooks

Reusable logic extraction.

```js
function useCounter(initial) {
  const [count, setCount] = useState(initial);

  const increment = () => setCount(prev => prev + 1);
  const decrement = () => setCount(prev => prev - 1);

  return { count, increment, decrement };
}
```

Benefits:
- Reusable
- Clean components
- Scalable architecture

---

# 🎯 9. Best Practices

✔ Split effects by responsibility  
✔ Keep dependency arrays accurate  
✔ Clean up subscriptions  
✔ Avoid unnecessary memoization  
✔ Prefer useReducer for complex state  

---

# ❌ 10. Common Mistakes

- Infinite loops in useEffect  
- Missing dependency  
- Using effect for simple calculations  
- Forgetting cleanup  
- Mutating state directly  

---

# 🧠 11. Interview Preparation

- Why hooks over classes?  
- Difference between useEffect & useLayoutEffect?  
- When to use useMemo vs useCallback?  
- Can hooks run conditionally?  
- What causes infinite loop in useEffect?  
- What is Strict Mode double execution?  

---

# 💎 Final Thought

> React Hooks make functional components scalable, readable, and production-ready.

---

<p align="center">
  Built with ⚛️ by Mihir Patel  
  Full Stack Developer | React Explorer
</p>

<p align="center">
  ⭐ Star this repository if it helps you grow!
</p>
