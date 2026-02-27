<!-- ================= HEADER ================= -->

<h1 align="center">
  🧱 Radix UI – Accessible & Unstyled React Primitives
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/React-18+-61DAFB?style=for-the-badge&logo=react" />
  <img src="https://img.shields.io/badge/Radix%20UI-Headless%20Components-black?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Accessibility-ARIA%20Compliant-success?style=for-the-badge" />
</p>

---

# 🚀 What is Radix UI?

> Radix UI is a set of low-level, accessible, unstyled React UI primitives.

It provides:
- Accessibility (ARIA, keyboard support)
- Headless components (no styling)
- Full customization freedom
- Composable component structure
- Production-ready behavior

Radix is used internally by:
- shadcn/ui
- Modern design systems
- Custom enterprise UI frameworks

---

# 🧠 Headless Component Architecture


::contentReference[oaicite:0]{index=0}


### 🔁 How Radix Works

1. Provides behavior (logic + accessibility)
2. You provide styles
3. Components are composable
4. Fully customizable UI

> Radix gives functionality, not design.

---

# 📦 Installation

Install specific components (modular system):

```bash
npm install @radix-ui/react-dialog
```

Each component is installed separately.

---

# 🎯 Dialog Example

```js
import * as Dialog from "@radix-ui/react-dialog";

function Example() {
  return (
    <Dialog.Root>
      <Dialog.Trigger>Open</Dialog.Trigger>

      <Dialog.Portal>
        <Dialog.Overlay className="overlay" />
        <Dialog.Content className="content">
          <Dialog.Title>Title</Dialog.Title>
          <Dialog.Description>
            Description goes here.
          </Dialog.Description>
          <Dialog.Close>Close</Dialog.Close>
        </Dialog.Content>
      </Dialog.Portal>
    </Dialog.Root>
  );
}
```

You must style `.overlay` and `.content` manually.

---

# 🧱 Core Radix Components

| Component | Purpose |
|------------|----------|
| Dialog | Modal |
| DropdownMenu | Dropdown |
| Tooltip | Tooltip |
| Popover | Floating UI |
| Tabs | Tab system |
| Accordion | Collapsible content |
| Slider | Range input |
| Switch | Toggle switch |

---

# 🎨 Styling with Tailwind

```js
<Dialog.Content className="bg-white p-6 rounded-lg shadow-lg">
```

Radix works perfectly with:
- Tailwind CSS
- CSS Modules
- Styled Components
- Vanilla CSS

---

# 🧠 Accessibility Features

Radix automatically handles:

✔ Keyboard navigation  
✔ Focus management  
✔ Screen reader support  
✔ ARIA attributes  
✔ Escape key handling  

---

# 🔄 Controlled vs Uncontrolled

Radix components support both:

### Uncontrolled

```js
<Dialog.Root>
```

### Controlled

```js
<Dialog.Root open={isOpen} onOpenChange={setIsOpen}>
```

---

# 📦 Tabs Example

```js
import * as Tabs from "@radix-ui/react-tabs";

<Tabs.Root defaultValue="tab1">
  <Tabs.List>
    <Tabs.Trigger value="tab1">Tab 1</Tabs.Trigger>
    <Tabs.Trigger value="tab2">Tab 2</Tabs.Trigger>
  </Tabs.List>

  <Tabs.Content value="tab1">Content 1</Tabs.Content>
  <Tabs.Content value="tab2">Content 2</Tabs.Content>
</Tabs.Root>
```

---

# ⚡ Why Use Radix?

✔ Full design freedom  
✔ Accessibility built-in  
✔ Lightweight  
✔ Modular imports  
✔ Composable structure  

---

# 📊 Radix vs shadcn/ui vs Chakra

| Feature | Radix | shadcn/ui | Chakra UI |
|----------|--------|------------|------------|
| Styled | No | Yes (custom) | Yes |
| Headless | Yes | Built on Radix | No |
| Accessibility | Excellent | Excellent | Good |
| Design Control | Full | High | Medium |
| Setup Complexity | Medium | Easy | Easy |

---

# 🏗 Project Structure Example

```
src/
 ├── components/
 │     ├── Dialog.jsx
 │     ├── Tabs.jsx
 │
 ├── styles/
 │
 └── App.jsx
```

---

# 🚀 Best Practices

✔ Combine with Tailwind  
✔ Keep components modular  
✔ Manage open state carefully  
✔ Use portals properly  
✔ Test keyboard navigation  

---

# 🔥 Common Mistakes

❌ Forgetting to style components  
❌ Ignoring accessibility attributes  
❌ Mixing too many UI systems  
❌ Not handling controlled state  
❌ Not testing focus behavior  

---

# 🧠 Interview Questions

- What is Radix UI?
- What are headless components?
- How accessibility is handled?
- Difference between Radix & Chakra?
- Why Radix is used in shadcn?

---

# 💎 Final Thought

> Radix UI gives you complete control over UI design while ensuring accessibility and production-ready behavior.

---

<p align="center">
  Built with 🧱 by Mihir Patel
</p>
