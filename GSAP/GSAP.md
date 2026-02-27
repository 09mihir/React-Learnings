<!-- ================= HEADER ================= -->

<h1 align="center">
  🚀 GSAP – GreenSock Animation Platform (Complete Developer Guide)
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/JavaScript-Animation-black?style=for-the-badge" />
  <img src="https://img.shields.io/badge/GSAP-High%20Performance%20Animations-88ce02?style=for-the-badge" />
  <img src="https://img.shields.io/badge/UI-Professional%20Motion-success?style=for-the-badge" />
</p>

---

# 🧠 What is GSAP?

> GSAP (GreenSock Animation Platform) is a high-performance JavaScript animation library used for professional-grade web animations.

It is used for:
- Advanced UI animations
- Scroll-based effects
- SVG animations
- 3D transforms
- Timeline sequencing
- Complex motion systems

Used by:
- Award-winning websites
- Product landing pages
- Interactive storytelling platforms

---

# 🎬 GSAP Animation Flow


::contentReference[oaicite:0]{index=0}


### 🔁 Animation Process

1. Select element
2. Define animation (from / to / timeline)
3. Configure duration & easing
4. Play animation
5. Optional: Trigger via scroll or interaction

---

# 📦 Installation

### Using npm

```bash
npm install gsap
```

### Using CDN

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
```

---

# 🎯 Basic Animation

```js
import gsap from "gsap";

gsap.to(".box", {
  x: 300,
  duration: 1,
});
```

Moves `.box` 300px on X axis.

---

# 🔄 from() vs to() vs fromTo()

```js
// Animate to value
gsap.to(".box", { x: 200 });

// Animate from value
gsap.from(".box", { opacity: 0 });

// Define both start and end
gsap.fromTo(".box", 
  { x: 0 }, 
  { x: 300 }
);
```

---

# ⏱ Timeline (Advanced Control)

```js
const tl = gsap.timeline();

tl.to(".box", { x: 200, duration: 1 })
  .to(".circle", { y: 100, duration: 1 })
  .to(".box", { rotation: 360, duration: 1 });
```

Timeline allows:
- Sequential animations
- Overlapping animations
- Fine-grained control

---

# 🎨 Easing Functions

```js
gsap.to(".box", {
  x: 200,
  ease: "power2.out",
});
```

Popular easings:
- power1
- power2
- bounce
- elastic
- expo

---

# 🌊 ScrollTrigger (Scroll Animations)

```js
import { ScrollTrigger } from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

gsap.to(".box", {
  scrollTrigger: ".box",
  x: 300,
  duration: 1,
});
```

ScrollTrigger allows:
- Scroll-based animations
- Pin sections
- Parallax effects
- Scroll progress control

---

# ⚡ React + GSAP Example

```js
import { useEffect, useRef } from "react";
import gsap from "gsap";

function Box() {
  const boxRef = useRef();

  useEffect(() => {
    gsap.to(boxRef.current, {
      x: 200,
      duration: 1,
    });
  }, []);

  return <div ref={boxRef} className="box" />;
}
```

> Always use `useRef` in React.

---

# 🧠 Key GSAP Features

| Feature | Purpose |
|----------|----------|
| gsap.to | Animate to value |
| gsap.from | Animate from value |
| gsap.fromTo | Define start & end |
| Timeline | Sequence animations |
| ScrollTrigger | Scroll-based animations |
| Stagger | Animate multiple elements |
| Ease | Smooth transitions |

---

# 🎭 Stagger Animation

```js
gsap.to(".item", {
  y: 50,
  stagger: 0.2,
});
```

Creates delay between elements.

---

# 🧩 SVG Animation Example

```js
gsap.to("svg path", {
  strokeDashoffset: 0,
  duration: 2,
});
```

Used for:
- Line drawing animations
- Icon animations
- Logo reveals

---

# ⚡ Performance Benefits

✔ Hardware-accelerated animations  
✔ Minimal layout thrashing  
✔ Highly optimized engine  
✔ Works smoothly across browsers  
✔ Better than CSS for complex motion  

---

# 📊 GSAP vs Framer Motion

| Feature | GSAP | Framer Motion |
|----------|------|---------------|
| Framework Agnostic | Yes | React Only |
| Timeline Control | Advanced | Basic |
| Scroll Animation | Powerful | Limited |
| Learning Curve | Medium | Easy |
| Performance | Excellent | Very Good |

---

# 🏗 Project Structure Example

```
src/
 ├── animations/
 │     ├── heroAnimation.js
 │     ├── scrollEffects.js
 │
 ├── components/
 │     ├── Hero.jsx
 │
 └── App.jsx
```

---

# 🔥 Common Mistakes

❌ Not cleaning animations in React  
❌ Overusing heavy scroll animations  
❌ Animating layout properties (top/left instead of transform)  
❌ Forgetting to register plugins  
❌ Running animations on every render  

---

# 🧠 Interview Questions

- What is GSAP?
- Difference between GSAP and CSS animations?
- What is Timeline?
- What is ScrollTrigger?
- Why GSAP is more performant?

---

# 💎 Final Thought

> GSAP is the industry standard for high-performance web animations.  
> Master timelines and scroll animations to build award-winning websites.

---

<p align="center">
  Built with 🚀 by Mihir Patel
</p>
