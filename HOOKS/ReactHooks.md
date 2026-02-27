<!-- ================= HEADER ================= -->

<h1 align="center">
  ⚛️ React Hooks – Developer Notes
</h1>

<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?size=22&duration=3000&color=61DAFB&center=true&vCenter=true&width=600&lines=Master+React+Hooks;Write+Cleaner+Functional+Components;Optimize+Performance+Like+a+Pro" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/React-18+-61DAFB?style=for-the-badge&logo=react" />
  <img src="https://img.shields.io/badge/Hooks-Complete%20Guide-blueviolet?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Level-Industry%20Ready-success?style=for-the-badge" />
</p>

---

## 📚 Table of Contents

- Introduction
- Rules of Hooks
- Core Hooks
- Additional Hooks
- Performance Hooks
- Advanced Hooks
- Custom Hooks
- Best Practices
- Interview Notes

---

# 🚀 Introduction

> 🔥 Hooks allow functional components to use state, lifecycle, and advanced React features.

Before Hooks:
- State → Class components
- Lifecycle → componentDidMount etc.

After Hooks:
- Clean functional components
- Reusable logic
- Better scalability

---

# 📏 Rules of Hooks

```js
// ✅ Correct
const [count, setCount] = useState(0);

// ❌ Wrong
if (condition) {
  useState(0);
}
```

✔ Only call at top level  
✔ Only inside React function  

---

# 🎯 useState

### Syntax

```js
const [state, setState] = useState(initialValue);
```

### Example

```js
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

- Asynchronous updates
- Causes re-render
- Never mutate directly

---

# 🌍 useEffect

Handles side effects:
- API calls
- Subscriptions
- Timers
- DOM updates

```js
useEffect(() => {
  console.log("Mounted");

  return () => {
    console.log("Cleanup");
  };
}, []);
```

### Dependency Cases

| Dependency | Behavior |
|------------|----------|
| `[]` | Runs once |
| `[value]` | Runs on change |
| No array | Every render |

---

# 🌐 useContext

Avoid prop drilling.

```js
const ThemeContext = createContext();

function Child() {
  const theme = useContext(ThemeContext);
  return <h1>{theme}</h1>;
}
```

---

# 📌 useRef

- Access DOM
- Persist mutable values
- No re-render trigger

```js
const inputRef = useRef(null);

useEffect(() => {
  inputRef.current.focus();
}, []);
```

---

# 🔁 useReducer

For complex state logic.

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

---

# 🧠 Performance Hooks

## useMemo

```js
const memoValue = useMemo(() => {
  return expensiveFunction(data);
}, [data]);
```

✔ Prevents recalculation  

---

## useCallback

```js
const memoFn = useCallback(() => {
  doSomething();
}, []);
```

✔ Prevents function recreation  

---

# ⚡ Advanced Hooks

## useLayoutEffect

Runs before browser paint.

```js
useLayoutEffect(() => {
  // DOM measurement
}, []);
```

---

## useImperativeHandle

Used with forwardRef.

```js
useImperativeHandle(ref, () => ({
  focus: () => inputRef.current.focus()
}));
```

---

## useTransition (React 18)

```js
const [isPending, startTransition] = useTransition();
```

Used for non-blocking UI updates.

---

# 🛠 Custom Hook Example

```js
function useCounter(initial) {
  const [count, setCount] = useState(initial);

  const increment = () => setCount(prev => prev + 1);
  const decrement = () => setCount(prev => prev - 1);

  return { count, increment, decrement };
}
```

---

# 🎯 Best Practices

✔ Split logic into multiple effects  
✔ Avoid unnecessary useMemo/useCallback  
✔ Clean up subscriptions  
✔ Prefer useReducer for complex state  
✔ Keep hooks readable  

---

# 🧠 Interview Quick Notes

- Why hooks over classes?
- Difference between useEffect & useLayoutEffect?
- When to use useMemo vs useCallback?
- Can hooks run conditionally?
- Why dependency array is important?

---

# 💎 Final Thought

> React Hooks make functional components powerful, scalable, and industry-ready.

---

<p align="center">
  Built with ⚛️ by Mihir Patel
</p>
