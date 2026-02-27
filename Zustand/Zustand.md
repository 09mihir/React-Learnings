<!-- ================= HEADER ================= -->

<h1 align="center">
  🐻 Zustand – Lightweight State Management for React
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/React-18+-61DAFB?style=for-the-badge&logo=react" />
  <img src="https://img.shields.io/badge/Zustand-Lightweight%20Store-8d6e63?style=for-the-badge" />
  <img src="https://img.shields.io/badge/State%20Management-Minimal%20API-success?style=for-the-badge" />
</p>

---

# 🚀 What is Zustand?

> Zustand is a small, fast, and scalable state management library for React.

It provides:
- Global state without boilerplate
- No reducers required
- Simple API
- No Provider needed
- Built-in middleware support

Perfect for:
- Medium to large apps
- Cleaner alternative to Redux
- Simpler global state handling

---

# 🧠 Zustand Architecture Flow


::contentReference[oaicite:0]{index=0}


### 🔁 Flow Explanation

1. Create a global store
2. Components subscribe using hook
3. State updates trigger re-render
4. Only subscribed components update

> Zustand avoids unnecessary re-renders.

---

# 📦 Installation

```bash
npm install zustand
```

---

# 🏗 Creating a Store

```js
// store/useCounterStore.js

import { create } from "zustand";

export const useCounterStore = create((set) => ({
  count: 0,
  increment: () => set((state) => ({ count: state.count + 1 })),
  decrement: () => set((state) => ({ count: state.count - 1 })),
}));
```

---

# 🎯 Using Zustand in Component

```js
import { useCounterStore } from "./store/useCounterStore";

function Counter() {
  const { count, increment, decrement } = useCounterStore();

  return (
    <>
      <h2>{count}</h2>
      <button onClick={increment}>+</button>
      <button onClick={decrement}>-</button>
    </>
  );
}
```

No Provider required ✅

---

# 🔥 Updating Partial State

```js
set({ count: 10 });
```

Zustand merges state automatically.

---

# 🧩 Selecting Specific State (Optimization)

```js
const count = useCounterStore((state) => state.count);
```

This prevents unnecessary re-renders.

---

# 🌍 Async State in Zustand

```js
export const useUserStore = create((set) => ({
  user: null,
  fetchUser: async () => {
    const response = await fetch("/api/user");
    const data = await response.json();
    set({ user: data });
  },
}));
```

Used directly in component:

```js
const fetchUser = useUserStore((state) => state.fetchUser);
```

---

# ⚡ Middleware Support

## Persist Middleware (LocalStorage)

```js
import { persist } from "zustand/middleware";

export const useStore = create(
  persist(
    (set) => ({
      count: 0,
      increment: () => set((s) => ({ count: s.count + 1 })),
    }),
    { name: "counter-storage" }
  )
);
```

---

## DevTools Middleware

```js
import { devtools } from "zustand/middleware";

export const useStore = create(
  devtools((set) => ({
    count: 0,
    increment: () => set((s) => ({ count: s.count + 1 })),
  }))
);
```

Works with Redux DevTools.

---

# 📊 Zustand vs Redux Toolkit

| Feature | Zustand | Redux Toolkit |
|----------|----------|--------------|
| Boilerplate | Minimal | Moderate |
| Reducers | Not required | Required |
| Provider | Not needed | Required |
| DevTools | Yes | Yes |
| Middleware | Yes | Yes |
| Learning Curve | Easy | Medium |

---

# 🧠 When to Use Zustand?

✔ Medium scale apps  
✔ Simpler global state  
✔ When Redux feels heavy  
✔ When Context API becomes messy  

Avoid when:
❌ Extremely large enterprise architecture  
❌ Complex normalized state required  

---

# 🏗 Folder Structure Example

```
src/
 ├── store/
 │     ├── useAuthStore.js
 │     ├── useCartStore.js
 │
 ├── components/
 ├── pages/
 └── App.jsx
```

---

# 🚀 Performance Advantages

✔ Selective subscriptions  
✔ No unnecessary renders  
✔ Simple store updates  
✔ No action types  

---

# 🔥 Common Mistakes

❌ Putting entire app state in one store  
❌ Not using selectors  
❌ Overusing global state  
❌ Forgetting middleware for persistence  

---

# 🧠 Interview Questions

- What is Zustand?
- How is it different from Redux?
- Why no Provider needed?
- How does subscription work?
- How to persist state?

---

# 💎 Final Thought

> Zustand gives you global state with minimal complexity.  
> It’s powerful, clean, and developer-friendly.

---

<p align="center">
  Built with 🐻 by Mihir Patel
</p>
