<!-- ================= HEADER ================= -->

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=venom&height=250&color=0:0f2027,50:203a43,100:61DAFB&text=React%20Hooks%20Mastery&fontSize=42&fontColor=ffffff&animation=fadeIn&fontAlignY=38"/>
</p>

<h1 align="center">⚛️ React Hooks – Complete Developer Guide</h1>

<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?size=22&duration=3000&color=61DAFB&center=true&vCenter=true&width=650&lines=Master+React+Hooks+Deeply;Write+Cleaner+Functional+Components;Optimize+Performance+Like+a+Pro;Industry-Level+Understanding" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/React-18+-61DAFB?style=for-the-badge&logo=react" />
  <img src="https://img.shields.io/badge/Hooks-Complete%20Reference-blueviolet?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Level-Industry%20Ready-success?style=for-the-badge" />
</p>

---

# 📚 Table of Contents

- Introduction
- Rules of Hooks
- Core Hooks
- useEffect (All Variations)
- Performance Hooks
- Advanced Hooks
- Custom Hooks
- Best Practices
- Interview Notes

---

# 🚀 Introduction

> Hooks allow functional components to use state, lifecycle logic, and advanced React features.

### Before Hooks:
- State → Class components  
- Lifecycle → componentDidMount, componentDidUpdate  

### After Hooks:
- Cleaner code  
- Reusable logic  
- Better scalability  
- Functional-first architecture  

---

# 📏 Rules of Hooks

```js
// ✅ Correct
const [count, setCount] = useState(0);

// ❌ Wrong
if (condition) {
  useState(0);
}
