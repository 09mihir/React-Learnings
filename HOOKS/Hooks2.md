<!-- ================= CYBERPUNK HEADER ================= -->

<h1 align="center">
  <span style="color:#00f7ff;">⚛️ REACT HOOKS</span>
</h1>

<h3 align="center">
  <span style="color:#ff00ff;">Cyberpunk Developer Notes</span>
</h3>

<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?size=24&duration=3000&color=00F7FF&center=true&vCenter=true&width=700&lines=Modern+React+Hooks;Functional+Components+Mastery;Performance+Optimization;Industry+Level+Concepts" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/React-18-00f7ff?style=for-the-badge&logo=react&logoColor=black"/>
  <img src="https://img.shields.io/badge/Hooks-Core+%2B+Advanced-ff00ff?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Mode-Dark%20Optimized-black?style=for-the-badge"/>
</p>

---

# 🌌 <span style="color:#00f7ff;">INTRODUCTION</span>

> <span style="color:#ff00ff;">Hooks allow functional components to control state, lifecycle, and performance without classes.</span>

Before Hooks:
- ❌ Class Components
- ❌ Lifecycle methods

After Hooks:
- ✅ Clean Functional Components
- ✅ Reusable Logic
- ✅ Better Scalability

---

# ⚠️ <span style="color:#ff4d4d;">RULES OF HOOKS</span>

```js
// ✅ Correct
const [count, setCount] = useState(0);

// ❌ Wrong
if (condition) {
  useState(0);
}
```

✔ Only call hooks at top level  
✔ Only inside React functions  

---

# 💠 <span style="color:#00ff99;">useState()</span>

### 🔹 Syntax

```js
const [state, setState] = useState(initialValue);
```

### 🔹 Example

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

### 🔹 Core Notes

- Triggers re-render
- Async updates
- Never mutate state directly

---

# 🌍 <span style="color:#ffaa00;">useEffect()</span>

> Handles side effects (API calls, timers, subscriptions)

```js
useEffect(() => {
  console.log("Mounted");

  return () => {
    console.log("Cleanup");
  };
}, []);
```

### Dependency Matrix

| Dependency | Execution |
|------------|------------|
| `[]` | Once |
| `[value]` | On change |
| No array | Every render |

---

# 🧬 <span style="color:#bb86fc;">useContext()</span>

Avoids prop drilling.

```js
const ThemeContext = createContext();

function Child() {
  const theme = useContext(ThemeContext);
  return <h1>{theme}</h1>;
}
```

---

# 🔮 <span style="color:#03dac6;">useRef()</span>

- Access DOM
- Store mutable value
- No re-render

```js
const inputRef = useRef(null);

useEffect(() => {
  inputRef.current.focus();
}, []);
```

---

# ⚡ <span style="color:#ff00ff;">Performance Hooks</span>

## 💎 useMemo()

```js
const memoValue = useMemo(() => {
  return expensiveFunction(data);
}, [data]);
```

✔ Prevents recalculation  

---

## 🔁 useCallback()

```js
const memoFn = useCallback(() => {
  doSomething();
}, []);
```

✔ Prevents function recreation  

---

# 🧠 <span style="color:#00f7ff;">Advanced Hooks</span>

## useReducer()

```js
function reducer(state, action) {
  switch (action.type) {
    case "increment":
      return { count: state.count + 1 };
    default:
      return state;
  }
}
```

---

## useLayoutEffect()

```js
useLayoutEffect(() => {
  // Runs before paint
}, []);
```

---

## useTransition() – React 18

```js
const [isPending, startTransition] = useTransition();
```

Non-blocking UI updates.

---

# 🛠 <span style="color:#00ffcc;">Custom Hook Example</span>

```js
function useCounter(initial) {
  const [count, setCount] = useState(initial);

  const increment = () => setCount(prev => prev + 1);
  const decrement = () => setCount(prev => prev - 1);

  return { count, increment, decrement };
}
```

---

# 🏆 <span style="color:#ff007f;">BEST PRACTICES</span>

✔ Split logic into multiple effects  
✔ Avoid unnecessary memoization  
✔ Clean up subscriptions  
✔ Prefer useReducer for complex state  
✔ Keep dependency arrays accurate  

---

# 🧠 <span style="color:#00f7ff;">INTERVIEW QUICK REVISION</span>

- Why hooks over classes?
- useEffect vs useLayoutEffect?
- useMemo vs useCallback?
- Can hooks run conditionally?
- Why dependency array matters?

---

<p align="center">
  <span style="color:#ff00ff;">⚛️ Built by Mihir Patel – Cyber Dev Mode Activated ⚛️</span>
</p>
