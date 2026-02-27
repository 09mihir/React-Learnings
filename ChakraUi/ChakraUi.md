<!-- ================= HEADER ================= -->

<h1 align="center">
  ⚡ Chakra UI – Modern & Accessible React Component Library
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/React-18+-61DAFB?style=for-the-badge&logo=react" />
  <img src="https://img.shields.io/badge/Chakra%20UI-Accessible%20Components-319795?style=for-the-badge" />
  <img src="https://img.shields.io/badge/UI-Developer%20Friendly-success?style=for-the-badge" />
</p>

---

# 🚀 What is Chakra UI?

> Chakra UI is a simple, modular, and accessible React component library.

It focuses on:
- Accessibility (ARIA support)
- Developer experience
- Clean design system
- Easy styling with props
- Built-in dark mode

Perfect for:
- SaaS apps
- Dashboards
- Landing pages
- Rapid UI development

---

# 🧠 Chakra UI Architecture


::contentReference[oaicite:0]{index=0}


### 🔁 How Chakra Works

1. Wrap app with `ChakraProvider`
2. Use prebuilt components
3. Style with style props
4. Customize theme globally
5. Enable dark/light mode easily

---

# 📦 Installation

```bash
npm install @chakra-ui/react @emotion/react @emotion/styled framer-motion
```

---

# 🏗 Setup

```js
import { ChakraProvider } from "@chakra-ui/react";

function App() {
  return (
    <ChakraProvider>
      <YourApp />
    </ChakraProvider>
  );
}
```

---

# 🎯 Basic Example

```js
import { Button } from "@chakra-ui/react";

function Example() {
  return (
    <Button colorScheme="teal">
      Click Me
    </Button>
  );
}
```

---

# 🧱 Core Components

| Component | Purpose |
|------------|----------|
| Button | Action button |
| Box | Layout wrapper |
| Flex | Flexbox layout |
| Grid | Grid layout |
| Input | Form input |
| Modal | Dialog |
| Drawer | Sidebar |
| Tabs | Tab navigation |

---

# 🎨 Styling with Props (Power Feature)

```js
<Box
  bg="blue.500"
  color="white"
  p={4}
  borderRadius="md"
>
  Styled Box
</Box>
```

Instead of writing CSS:
- Use props like `bg`, `p`, `mt`, `color`

---

# 🌗 Dark Mode (Built-in)

```js
import { useColorMode, Button } from "@chakra-ui/react";

function ToggleTheme() {
  const { toggleColorMode } = useColorMode();

  return <Button onClick={toggleColorMode}>Toggle Mode</Button>;
}
```

Automatically adapts theme.

---

# 🎨 Custom Theme

```js
import { extendTheme } from "@chakra-ui/react";

const theme = extendTheme({
  colors: {
    brand: {
      500: "#1E40AF",
    },
  },
});
```

Use in provider:

```js
<ChakraProvider theme={theme}>
```

---

# 📱 Responsive Design

```js
<Box
  w={["100%", "50%", "25%"]}
>
  Responsive Box
</Box>
```

Breakpoints:
- base
- sm
- md
- lg
- xl

---

# 📦 Modal Example

```js
import {
  Modal,
  ModalOverlay,
  ModalContent,
  ModalHeader,
  ModalBody,
  ModalFooter,
  Button,
  useDisclosure,
} from "@chakra-ui/react";

function ExampleModal() {
  const { isOpen, onOpen, onClose } = useDisclosure();

  return (
    <>
      <Button onClick={onOpen}>Open</Button>

      <Modal isOpen={isOpen} onClose={onClose}>
        <ModalOverlay />
        <ModalContent>
          <ModalHeader>Modal Title</ModalHeader>
          <ModalBody>Content here</ModalBody>
          <ModalFooter>
            <Button onClick={onClose}>Close</Button>
          </ModalFooter>
        </ModalContent>
      </Modal>
    </>
  );
}
```

---

# ⚡ Layout with Flex

```js
<Flex justify="space-between" align="center">
  <Box>Left</Box>
  <Box>Right</Box>
</Flex>
```

---

# 🧠 Chakra vs MUI

| Feature | Chakra UI | MUI |
|----------|------------|------|
| Styling System | Style props | sx / styled |
| Learning Curve | Easy | Medium |
| Customization | High | High |
| Design System | Minimal | Material Design |
| Dark Mode | Built-in | Manual setup |

---

# 🏗 Project Structure Example

```
src/
 ├── theme/
 │     ├── theme.js
 │
 ├── components/
 │     ├── Navbar.jsx
 │     ├── Sidebar.jsx
 │
 └── App.jsx
```

---

# 🚀 Best Practices

✔ Use style props effectively  
✔ Extend theme instead of inline heavy styles  
✔ Use responsive arrays  
✔ Avoid mixing too many UI libraries  
✔ Keep consistent spacing scale  

---

# 🔥 Common Mistakes

❌ Not wrapping app with ChakraProvider  
❌ Overusing inline styling  
❌ Ignoring accessibility props  
❌ Mixing raw CSS unnecessarily  
❌ Not using theme system properly  

---

# 🧠 Interview Questions

- What is Chakra UI?
- Difference between Chakra & MUI?
- How dark mode works?
- What is style props system?
- How theming works?

---

# 💎 Final Thought

> Chakra UI provides accessible, flexible, and modern components with minimal setup.  
> Perfect for building clean, scalable React applications.

---

<p align="center">
  Built with ⚡ by Mihir Patel
</p>
