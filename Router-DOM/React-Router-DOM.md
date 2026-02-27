<!-- ================= HEADER ================= -->

<h1 align="center">
  ⚛️ React Router DOM – Complete Developer Guide
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/React-18+-61DAFB?style=for-the-badge&logo=react" />
  <img src="https://img.shields.io/badge/React%20Router-DOM-CA4245?style=for-the-badge&logo=reactrouter" />
  <img src="https://img.shields.io/badge/Routing-Client%20Side-success?style=for-the-badge" />
</p>

---

# 🚀 What is React Router DOM?

> React Router DOM is a library for handling **client-side routing** in React applications.

It allows you to:
- Navigate between pages
- Create dynamic routes
- Handle URL parameters
- Protect routes
- Manage nested layouts

---

# 🌐 Client-Side Routing Architecture


::contentReference[oaicite:0]{index=0}


### 🔁 Routing Flow

1. User clicks `<Link>`
2. URL changes (without full page reload)
3. Router matches route
4. Corresponding component renders
5. UI updates

> React Router uses the **History API** internally.

---

# 📦 Installation

```bash
npm install react-router-dom
```

---

# 🏗 Basic Setup (React Router v6+)

```js
import { BrowserRouter, Routes, Route } from "react-router-dom";
import Home from "./Home";
import About from "./About";

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
      </Routes>
    </BrowserRouter>
  );
}
```

---

# 🔗 Navigation with Link

```js
import { Link } from "react-router-dom";

<Link to="/">Home</Link>
<Link to="/about">About</Link>
```

> Prevents full page reload.

---

# 🎯 useNavigate Hook

Programmatic navigation.

```js
import { useNavigate } from "react-router-dom";

function Login() {
  const navigate = useNavigate();

  const handleLogin = () => {
    navigate("/dashboard");
  };

  return <button onClick={handleLogin}>Login</button>;
}
```

---

# 📌 Dynamic Routes

```js
<Route path="/user/:id" element={<User />} />
```

Access parameter:

```js
import { useParams } from "react-router-dom";

function User() {
  const { id } = useParams();
  return <h2>User ID: {id}</h2>;
}
```

---

# 📦 Nested Routes (Layout System)

```js
<Route path="/dashboard" element={<Dashboard />}>
  <Route path="profile" element={<Profile />} />
  <Route path="settings" element={<Settings />} />
</Route>
```

Inside Dashboard:

```js
import { Outlet } from "react-router-dom";

function Dashboard() {
  return (
    <>
      <h1>Dashboard</h1>
      <Outlet />
    </>
  );
}
```

---

# 🔐 Protected Routes

```js
function ProtectedRoute({ children }) {
  const isAuth = true;

  return isAuth ? children : <Navigate to="/login" />;
}
```

Usage:

```js
<Route
  path="/dashboard"
  element={
    <ProtectedRoute>
      <Dashboard />
    </ProtectedRoute>
  }
/>
```

---

# 🔄 useLocation Hook

```js
import { useLocation } from "react-router-dom";

const location = useLocation();
console.log(location.pathname);
```

Used for:
- Tracking current route
- Analytics
- Conditional rendering

---

# 🧠 Query Parameters

URL:
```
/search?query=react
```

Access:

```js
import { useSearchParams } from "react-router-dom";

const [searchParams] = useSearchParams();
const query = searchParams.get("query");
```

---

# 📊 Routing Concepts Summary

| Feature | Purpose |
|----------|----------|
| BrowserRouter | Wraps app |
| Routes | Holds route definitions |
| Route | Defines path |
| Link | Navigation |
| useNavigate | Programmatic redirect |
| useParams | Dynamic route data |
| Outlet | Nested layout |
| Navigate | Redirect component |

---

# 🏗 Routing Strategies (Industry Level)

### Small App
- Basic Routes
- useNavigate

### Medium App
- Nested Routes
- Layout system
- Protected routes

### Large App
- Role-based access
- Lazy loading routes
- Code splitting
- Route-based authentication

---

# ⚡ Lazy Loading Routes

```js
import { lazy, Suspense } from "react";

const Dashboard = lazy(() => import("./Dashboard"));

<Suspense fallback={<p>Loading...</p>}>
  <Dashboard />
</Suspense>
```

Improves performance.

---

# 🔥 Common Mistakes

❌ Forgetting `BrowserRouter`  
❌ Using `<a>` instead of `<Link>`  
❌ Wrong nested route structure  
❌ Not handling 404 routes  

---

# 🧠 Interview Questions

- Difference between client-side & server-side routing?
- What is dynamic routing?
- How to protect routes?
- How nested routing works?
- How to handle 404 page?

---

# 💎 Final Thought

> React Router DOM enables seamless SPA navigation and scalable routing architecture.

---

<p align="center">
  Built with ⚛️ by Mihir Patel
</p>
