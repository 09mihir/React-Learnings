<!-- ================= HEADER ================= -->

<h1 align="center">
  🧩 shadcn/ui – Modern UI Components for React & Next.js
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/React-18+-61DAFB?style=for-the-badge&logo=react" />
  <img src="https://img.shields.io/badge/shadcn/ui-Accessible%20Components-black?style=for-the-badge" />
  <img src="https://img.shields.io/badge/TailwindCSS-Utility%20First-38BDF8?style=for-the-badge&logo=tailwindcss" />
  <img src="https://img.shields.io/badge/UI-Modern%20Design-success?style=for-the-badge" />
</p>

---

# 🚀 What is shadcn/ui?

> shadcn/ui is a collection of beautifully designed, accessible components built using **Radix UI + Tailwind CSS**.

Unlike traditional UI libraries:
- It is not installed as a package
- You copy components into your project
- Full control over styling
- Fully customizable
- Built for modern apps

Perfect for:
- SaaS dashboards
- Modern web apps
- Admin panels
- Next.js projects

---

# 🧠 Architecture Overview


::contentReference[oaicite:0]{index=0}


### 🔁 How It Works

1. Uses Radix UI primitives (accessibility)
2. Styled with Tailwind CSS
3. Copied directly into your project
4. Fully customizable
5. No runtime dependency lock-in

---

# 📦 Installation (Next.js Example)

```bash
npx shadcn-ui@latest init
```

Follow prompts to:
- Configure Tailwind
- Setup components folder
- Setup aliases

---

# 📁 Folder Structure

```
src/
 ├── components/
 │     ├── ui/
 │          ├── button.tsx
 │          ├── card.tsx
 │          ├── dialog.tsx
 │
 ├── lib/
 │     ├── utils.ts
 │
 └── app/
```

---

# 🎯 Adding a Component

Example:

```bash
npx shadcn-ui@latest add button
```

It generates:

```
components/ui/button.tsx
```

---

# 🧱 Button Example

```tsx
import { Button } from "@/components/ui/button";

<Button>Click Me</Button>
```

Variants:

```tsx
<Button variant="outline">Outline</Button>
<Button variant="destructive">Delete</Button>
<Button size="lg">Large</Button>
```

---

# 🎨 Customization (Full Control)

Because components are copied locally:

```tsx
export function Button({ className, ...props }) {
  return (
    <button
      className={`rounded-lg px-4 py-2 ${className}`}
      {...props}
    />
  );
}
```

You can:
- Modify styles
- Add animations
- Change structure
- Extend variants

---

# 🧩 Card Example

```tsx
import {
  Card,
  CardContent,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";

<Card>
  <CardHeader>
    <CardTitle>Dashboard</CardTitle>
  </CardHeader>
  <CardContent>
    Welcome back!
  </CardContent>
</Card>
```

---

# 🔐 Dialog (Modal) Example

```tsx
import {
  Dialog,
  DialogContent,
  DialogTrigger,
} from "@/components/ui/dialog";

<Dialog>
  <DialogTrigger>Open</DialogTrigger>
  <DialogContent>
    Modal Content
  </DialogContent>
</Dialog>
```

Built on Radix UI for accessibility.

---

# 🌗 Dark Mode Support

shadcn/ui uses Tailwind dark mode.

```tsx
<html className="dark">
```

Or toggle using:

```tsx
className="bg-white dark:bg-black"
```

---

# 🧠 Why shadcn/ui is Different?

| Feature | shadcn/ui | MUI | Ant Design |
|----------|------------|------|------------|
| Fully Customizable | Yes | Limited | Limited |
| Precompiled Styles | No | Yes | Yes |
| Tailwind Based | Yes | No | No |
| Accessibility | Radix-based | Yes | Yes |
| Bundle Size | Minimal | Larger | Larger |

---

# ⚡ Advantages

✔ No dependency lock-in  
✔ Full control over components  
✔ Tailwind-based styling  
✔ Accessible by default  
✔ Works perfectly with Next.js  

---

# 🏗 Example Usage in Layout

```tsx
<div className="grid gap-4 md:grid-cols-2">
  <Card>
    <CardContent>Card 1</CardContent>
  </Card>

  <Card>
    <CardContent>Card 2</CardContent>
  </Card>
</div>
```

---

# 🚀 Best Practices

✔ Keep UI components modular  
✔ Customize theme variables  
✔ Use consistent spacing scale  
✔ Extend variants carefully  
✔ Avoid over-modifying core structure  

---

# 🔥 Common Mistakes

❌ Not setting up Tailwind properly  
❌ Ignoring accessibility props  
❌ Overwriting component logic  
❌ Mixing too many UI systems  
❌ Forgetting dark mode testing  

---

# 🧠 Interview Questions

- What is shadcn/ui?
- Why is it different from MUI?
- How Radix UI helps?
- Why copy components locally?
- How theming works in shadcn?

---

# 💎 Final Thought

> shadcn/ui gives you design-system power with full customization.  
> It’s modern, flexible, and built for serious React developers.

---

<p align="center">
  Built with 🧩 by Mihir Patel
</p>
