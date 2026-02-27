<!-- ================= HEADER ================= -->

<h1 align="center">
  🌬️ Tailwind CSS – Utility-First CSS Framework Guide
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/CSS-Utility%20First-38BDF8?style=for-the-badge&logo=tailwindcss" />
  <img src="https://img.shields.io/badge/Framework-TailwindCSS-0EA5E9?style=for-the-badge" />
  <img src="https://img.shields.io/badge/UI-Rapid%20Development-success?style=for-the-badge" />
</p>

---

# 🚀 What is Tailwind CSS?

> Tailwind CSS is a utility-first CSS framework for rapidly building custom user interfaces.

Instead of writing custom CSS:

```css
.button {
  background-color: blue;
  padding: 1rem;
}
```

You use utility classes directly in HTML:

```html
<button class="bg-blue-500 p-4">
```

---

# 🧠 Utility-First Concept


::contentReference[oaicite:0]{index=0}


### 🔁 How Tailwind Works

1. Use predefined utility classes
2. Combine classes for styling
3. No separate CSS file needed
4. Fully customizable via config

---

# 📦 Installation (Vite / React Example)

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

---

# ⚙️ tailwind.config.js Setup

```js
export default {
  content: ["./index.html", "./src/**/*.{js,ts,jsx,tsx}"],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

---

# 🎯 Basic Styling Example

```html
<div class="bg-blue-500 text-white p-6 rounded-lg shadow-lg">
  Tailwind Card
</div>
```

---

# 🧱 Core Utility Categories

| Category | Example |
|----------|----------|
| Colors | bg-blue-500 |
| Spacing | p-4, m-2 |
| Flexbox | flex, items-center |
| Grid | grid, grid-cols-2 |
| Typography | text-xl, font-bold |
| Border | border, rounded |
| Shadow | shadow-md |
| Width/Height | w-64, h-32 |

---

# 📱 Responsive Design

Tailwind uses mobile-first breakpoints.

```html
<div class="w-full md:w-1/2 lg:w-1/3">
```

Breakpoints:
- sm
- md
- lg
- xl
- 2xl

---

# 🌗 Dark Mode

Enable in config:

```js
darkMode: "class",
```

Usage:

```html
<div class="bg-white dark:bg-black text-black dark:text-white">
```

---

# 🎨 Hover & Focus States

```html
<button class="bg-blue-500 hover:bg-blue-700 focus:ring-2">
  Hover Me
</button>
```

---

# 🧩 Flexbox Example

```html
<div class="flex justify-between items-center">
  <div>Left</div>
  <div>Right</div>
</div>
```

---

# 🧱 Grid Example

```html
<div class="grid grid-cols-3 gap-4">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>
```

---

# 🎨 Customizing Theme

```js
theme: {
  extend: {
    colors: {
      brand: "#1E40AF",
    },
  },
},
```

Usage:

```html
<div class="bg-brand">
```

---

# ⚡ @apply Directive (Reusable Classes)

```css
.btn {
  @apply bg-blue-500 text-white p-4 rounded-lg;
}
```

---

# 🧠 Tailwind vs Traditional CSS

| Feature | Tailwind | Traditional CSS |
|----------|-----------|----------------|
| Speed | Fast | Slower |
| Reusability | Utility-based | Class-based |
| File Size | Optimized | Can grow large |
| Customization | Config-driven | Manual |
| Learning Curve | Medium | Easy |

---

# 🏗 Project Structure Example

```
src/
 ├── components/
 │     ├── Navbar.jsx
 │     ├── Card.jsx
 │
 ├── styles/
 │     ├── index.css
 │
 └── App.jsx
```

---

# 🚀 Advanced Features

✔ JIT Mode (Just-In-Time compiler)  
✔ Arbitrary values (`w-[450px]`)  
✔ Plugins support  
✔ Animation utilities  
✔ Container queries  

---

# 🔥 Common Mistakes

❌ Too many utility classes without structure  
❌ Not using reusable components  
❌ Ignoring responsive design  
❌ Mixing heavy custom CSS unnecessarily  
❌ Not configuring purge/content paths  

---

# 🧠 Interview Questions

- What is utility-first CSS?
- How Tailwind improves development speed?
- What is JIT mode?
- How dark mode works?
- Difference between Tailwind & Bootstrap?

---

# 💎 Final Thought

> Tailwind CSS accelerates UI development with flexibility and full design control.  
> Perfect for modern React and frontend applications.

---

<p align="center">
  Built with 🌬️ by Mihir Patel
</p>
