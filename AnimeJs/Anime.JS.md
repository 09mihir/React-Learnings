<!-- ================= HEADER ================= -->

<h1 align="center">
  🎨 Anime.js – Lightweight JavaScript Animation Engine
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/JavaScript-Animation-black?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Anime.js-Lightweight%20Engine-ff4081?style=for-the-badge" />
  <img src="https://img.shields.io/badge/UI-Smooth%20Motion-success?style=for-the-badge" />
</p>

---

# 🚀 What is Anime.js?

> Anime.js is a lightweight JavaScript animation library for animating CSS properties, SVG, DOM attributes, and JavaScript objects.

It is:
- Small in size
- Easy to use
- Powerful for UI animations
- Great for SVG motion
- Flexible with timelines

Perfect for:
- Landing pages
- Micro-interactions
- SVG animations
- Portfolio animations
- UI transitions

---

# 🎬 Animation Workflow


::contentReference[oaicite:0]{index=0}


### 🔁 Animation Flow

1. Select target element
2. Define animation properties
3. Set duration & easing
4. Execute animation
5. Optional timeline sequencing

---

# 📦 Installation

### Using npm

```bash
npm install animejs
```

### Using CDN

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/animejs/3.2.1/anime.min.js"></script>
```

---

# 🎯 Basic Animation

```js
import anime from "animejs";

anime({
  targets: ".box",
  translateX: 250,
  duration: 1000,
});
```

Moves `.box` 250px to right.

---

# 🔄 Animate Multiple Properties

```js
anime({
  targets: ".box",
  translateX: 250,
  rotate: "1turn",
  backgroundColor: "#ff0000",
  duration: 1500,
});
```

Supports:
- Transform
- Opacity
- Colors
- Scale
- Rotation

---

# ⏱ Timeline (Sequential Animation)

```js
const tl = anime.timeline();

tl.add({
  targets: ".box",
  translateX: 250,
})
.add({
  targets: ".circle",
  translateY: 100,
})
.add({
  targets: ".box",
  rotate: 360,
});
```

Timeline allows:
- Sequencing
- Delays
- Chaining animations

---

# 🎨 Easing Options

```js
anime({
  targets: ".box",
  translateX: 250,
  easing: "easeInOutQuad",
});
```

Popular easings:
- linear
- easeInOutQuad
- easeOutElastic
- easeInBounce

---

# 🌊 Stagger Animation

```js
anime({
  targets: ".item",
  translateY: 50,
  delay: anime.stagger(100),
});
```

Creates stagger effect between elements.

---

# 🧩 SVG Animation Example

```js
anime({
  targets: "path",
  strokeDashoffset: [anime.setDashoffset, 0],
  duration: 2000,
  easing: "easeInOutSine",
});
```

Perfect for:
- Logo animations
- Line drawing effects
- Icon motion

---

# 🎮 Animate JavaScript Objects

```js
let obj = { value: 0 };

anime({
  targets: obj,
  value: 100,
  round: 1,
  duration: 2000,
  update: function() {
    console.log(obj.value);
  }
});
```

Useful for:
- Counters
- Data animations
- Progress indicators

---

# ⚡ React + Anime.js Example

```js
import { useEffect } from "react";
import anime from "animejs";

function Box() {
  useEffect(() => {
    anime({
      targets: ".box",
      translateX: 200,
      duration: 1000,
    });
  }, []);

  return <div className="box" />;
}
```

---

# 🧠 Core Features

| Feature | Purpose |
|----------|----------|
| targets | Element selection |
| duration | Animation time |
| delay | Start delay |
| easing | Smooth transition |
| timeline | Sequence animations |
| stagger | Multi-element animation |
| loop | Repeat animation |

---

# 🔁 Loop Animation

```js
anime({
  targets: ".box",
  translateX: 200,
  direction: "alternate",
  loop: true,
});
```

---

# 📊 Anime.js vs GSAP

| Feature | Anime.js | GSAP |
|----------|-----------|------|
| Bundle Size | Smaller | Larger |
| Timeline | Yes | Advanced |
| Scroll Animation | Manual | Built-in (ScrollTrigger) |
| Performance | Very Good | Excellent |
| Ease of Use | Easy | Moderate |

---

# 🏗 Project Structure Example

```
src/
 ├── animations/
 │     ├── heroAnimation.js
 │     ├── svgEffects.js
 │
 ├── components/
 │     ├── Hero.jsx
 │
 └── App.jsx
```

---

# 🔥 Common Mistakes

❌ Not cleaning animations in React  
❌ Animating layout properties heavily  
❌ Too many simultaneous animations  
❌ Forgetting easing configuration  
❌ Not optimizing SVG paths  

---

# 🧠 Interview Questions

- What is Anime.js?
- Difference between Anime.js & GSAP?
- How timeline works?
- How to animate SVG?
- How to animate multiple elements?

---

# 💎 Final Thought

> Anime.js provides simple yet powerful animation capabilities with minimal setup.  
> Perfect for clean UI motion and lightweight animation systems.

---

<p align="center">
  Built with 🎨 by Mihir Patel
</p>
