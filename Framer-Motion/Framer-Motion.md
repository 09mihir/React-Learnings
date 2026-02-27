<!-- ================= HEADER ================= -->

<h1 align="center">
  🎬 React + Framer Motion – Animation Mastery Guide
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/React-18+-61DAFB?style=for-the-badge&logo=react" />
  <img src="https://img.shields.io/badge/Framer%20Motion-Animation%20Library-ff4c8b?style=for-the-badge" />
  <img src="https://img.shields.io/badge/UI-Modern%20Animations-success?style=for-the-badge" />
</p>

---

# 🚀 What is Framer Motion?

> Framer Motion is a powerful animation library for React.

It allows you to:
- Animate components easily
- Create smooth page transitions
- Build gesture-based animations
- Handle layout animations
- Add spring physics effects

Perfect for:
- Portfolio websites
- Modern UI/UX
- Landing pages
- Micro-interactions
- Production-grade animation systems

---

# 🧠 Animation Flow in React


::contentReference[oaicite:0]{index=0}


### 🔁 Animation Process

1. Component mounts
2. Initial state applied
3. Animate state triggered
4. Transition controls animation timing
5. Exit animation (optional)

---

# 📦 Installation

```bash
npm install framer-motion
```

---

# 🎯 Basic Animation

```js
import { motion } from "framer-motion";

function Box() {
  return (
    <motion.div
      initial={{ opacity: 0 }}
      animate={{ opacity: 1 }}
      transition={{ duration: 1 }}
    >
      Hello Animation
    </motion.div>
  );
}
```

---

# 🧱 Core Animation Props

| Prop | Purpose |
|-------|----------|
| initial | Starting state |
| animate | End state |
| exit | Unmount animation |
| transition | Timing configuration |
| whileHover | Hover animation |
| whileTap | Click animation |

---

# 🎨 Hover & Tap Animations

```js
<motion.button
  whileHover={{ scale: 1.1 }}
  whileTap={{ scale: 0.9 }}
>
  Click Me
</motion.button>
```

---

# 🌊 Spring Animation

```js
<motion.div
  animate={{ x: 200 }}
  transition={{ type: "spring", stiffness: 100 }}
/>
```

Spring gives:
- Natural motion
- Smooth feel
- Physics-based movement

---

# 🎬 Variants (Reusable Animations)

```js
const boxVariants = {
  hidden: { opacity: 0, y: -50 },
  visible: { opacity: 1, y: 0 },
};

<motion.div
  variants={boxVariants}
  initial="hidden"
  animate="visible"
/>
```

> Variants help organize complex animations.

---

# 🔄 Animate Presence (Exit Animation)

```js
import { AnimatePresence } from "framer-motion";

<AnimatePresence>
  {isVisible && (
    <motion.div
      initial={{ opacity: 0 }}
      animate={{ opacity: 1 }}
      exit={{ opacity: 0 }}
    />
  )}
</AnimatePresence>
```

Used for:
- Modal fade-out
- Route transitions
- Component removal animations

---

# 🧭 Page Transitions (React Router + Framer Motion)

```js
<motion.div
  initial={{ opacity: 0, x: -100 }}
  animate={{ opacity: 1, x: 0 }}
  exit={{ opacity: 0, x: 100 }}
  transition={{ duration: 0.5 }}
>
  Page Content
</motion.div>
```

Combine with `AnimatePresence` for smooth routing.

---

# 🧠 Layout Animations

```js
<motion.div layout />
```

Automatically animates:
- Position changes
- Size changes
- Layout shifts

---

# 🎮 Gesture Animations

```js
<motion.div
  drag
  dragConstraints={{ left: -100, right: 100 }}
/>
```

Supports:
- Drag
- Pan
- Tap
- Hover

---

# ⚡ Performance Optimization

✔ Use `layout` carefully  
✔ Avoid heavy animation loops  
✔ Keep transitions lightweight  
✔ Use `will-change` if needed  
✔ Avoid unnecessary re-renders  

---

# 📊 Framer Motion vs CSS Animation

| Feature | Framer Motion | CSS |
|----------|---------------|------|
| React integration | Excellent | Limited |
| Physics-based | Yes | No |
| Gesture support | Yes | No |
| Layout animation | Yes | Manual |
| Easy state sync | Yes | Difficult |

---

# 🏗 Project Structure Example

```
src/
 ├── animations/
 │     ├── variants.js
 │
 ├── components/
 │     ├── AnimatedCard.jsx
 │
 ├── pages/
 │     ├── Home.jsx
 │
 └── App.jsx
```

---

# 🔥 Common Mistakes

❌ Forgetting AnimatePresence for exit  
❌ Overusing animations  
❌ Not defining transition properly  
❌ Heavy layout animations everywhere  
❌ Animating too many elements at once  

---

# 🧠 Interview Questions

- What is Framer Motion?
- Difference between CSS & Framer Motion?
- What are variants?
- What is AnimatePresence?
- How layout animation works?

---

# 💎 Final Thought

> Framer Motion makes modern UI animations simple, powerful, and production-ready.  
> Master it to build premium frontend experiences.

---

<p align="center">
  Built with 🎬 by Mihir Patel
</p>
