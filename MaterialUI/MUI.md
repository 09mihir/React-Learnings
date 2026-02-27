<!-- ================= HEADER ================= -->

<h1 align="center">
  🎨 MUI (Material UI) – Complete React Component Library Guide
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/React-18+-61DAFB?style=for-the-badge&logo=react" />
  <img src="https://img.shields.io/badge/MUI-Material%20UI-007FFF?style=for-the-badge&logo=mui" />
  <img src="https://img.shields.io/badge/UI-Production%20Ready-success?style=for-the-badge" />
</p>

---

# 🚀 What is MUI?

> MUI (Material UI) is a popular React component library implementing Google’s Material Design system.

It provides:
- Prebuilt UI components
- Responsive layout system
- Customizable themes
- Accessibility support
- Production-ready design system

Perfect for:
- Dashboards
- Admin panels
- SaaS apps
- Enterprise applications

---

# 🧠 MUI Architecture Overview


::contentReference[oaicite:0]{index=0}


### 🔁 How MUI Works

1. Install MUI
2. Wrap app with ThemeProvider (optional)
3. Use prebuilt components
4. Customize with sx / styled API
5. Extend theme globally

---

# 📦 Installation

```bash
npm install @mui/material @emotion/react @emotion/styled
```

Optional icons:

```bash
npm install @mui/icons-material
```

---

# 🎯 Basic Example

```js
import Button from "@mui/material/Button";

function App() {
  return (
    <Button variant="contained" color="primary">
      Click Me
    </Button>
  );
}
```

---

# 🧱 Core Components

| Component | Purpose |
|------------|----------|
| Button | Actions |
| TextField | Input |
| Typography | Text styling |
| Card | Content container |
| Grid | Layout system |
| Box | Utility wrapper |
| AppBar | Top navigation |
| Drawer | Sidebar |

---

# 🎨 Using the `sx` Prop (Styling)

```js
<Box
  sx={{
    backgroundColor: "primary.main",
    padding: 2,
    borderRadius: 2,
  }}
>
  Styled Box
</Box>
```

`sx` allows:
- Inline theme-based styling
- Responsive values
- Cleaner customization

---

# 🌗 Theming (Custom Theme)

```js
import { createTheme, ThemeProvider } from "@mui/material/styles";

const theme = createTheme({
  palette: {
    primary: {
      main: "#ff5722",
    },
  },
});

function App() {
  return (
    <ThemeProvider theme={theme}>
      <Button variant="contained">Custom Theme</Button>
    </ThemeProvider>
  );
}
```

---

# 📱 Responsive Grid Layout

```js
import Grid from "@mui/material/Grid";

<Grid container spacing={2}>
  <Grid item xs={12} md={6}>
    Left
  </Grid>
  <Grid item xs={12} md={6}>
    Right
  </Grid>
</Grid>
```

Breakpoints:
- xs (0px)
- sm (600px)
- md (900px)
- lg (1200px)
- xl (1536px)

---

# 📦 Form Example

```js
import TextField from "@mui/material/TextField";
import Button from "@mui/material/Button";

function Form() {
  return (
    <>
      <TextField label="Email" variant="outlined" />
      <Button variant="contained">Submit</Button>
    </>
  );
}
```

---

# 🧭 Navigation Example

```js
import AppBar from "@mui/material/AppBar";
import Toolbar from "@mui/material/Toolbar";
import Typography from "@mui/material/Typography";

<AppBar position="static">
  <Toolbar>
    <Typography variant="h6">My App</Typography>
  </Toolbar>
</AppBar>
```

---

# 🧠 Styled API

```js
import { styled } from "@mui/material/styles";

const CustomButton = styled(Button)({
  backgroundColor: "black",
  color: "white",
});
```

---

# ⚡ Dark Mode Setup

```js
const darkTheme = createTheme({
  palette: {
    mode: "dark",
  },
});
```

Wrap with ThemeProvider.

---

# 📊 MUI vs Tailwind CSS

| Feature | MUI | Tailwind |
|----------|------|----------|
| Prebuilt Components | Yes | No |
| Utility-first | No | Yes |
| Theming | Built-in | Manual |
| Learning Curve | Medium | Easy |
| Enterprise Ready | Yes | Yes |

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
 ├── pages/
 │
 └── App.jsx
```

---

# 🚀 Advanced Components

✔ DataGrid  
✔ Dialog  
✔ Modal  
✔ Snackbar  
✔ Tabs  
✔ Accordion  
✔ Stepper  

---

# 🔥 Common Mistakes

❌ Overriding styles incorrectly  
❌ Not using ThemeProvider  
❌ Mixing too many styling approaches  
❌ Ignoring accessibility props  
❌ Overusing inline sx logic  

---

# 🧠 Interview Questions

- What is MUI?
- Difference between sx & styled?
- How theming works?
- How to enable dark mode?
- Why use MUI over custom CSS?

---

# 💎 Final Thought

> MUI accelerates UI development with scalable and consistent design.  
> Perfect for building professional-grade React applications.

---

<p align="center">
  Built with 🎨 by Mihir Patel
</p>
