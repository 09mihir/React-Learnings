<!-- ================= HEADER ================= -->

<h1 align="center">
  ⚛️ React Core Concepts – Props, Hierarchy, Conditional Rendering & More
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/React-18+-61DAFB?style=for-the-badge&logo=react" />
  <img src="https://img.shields.io/badge/Core%20Concepts-Frontend%20Fundamentals-ff6b6b?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Architecture-Component%20Based-success?style=for-the-badge" />
</p>

---

# 🧠 1️⃣ Parent-Child Hierarchy in React

> React applications are built using a **component tree structure**.

Each component can:
- Pass data downward (props)
- Trigger events upward
- Share state via lifting or global state

---

## 🌳 Component Hierarchy Diagram


::contentReference[oaicite:0]{index=0}


### Hierarchy Example

```
App
 ├── Navbar
 ├── Sidebar
 └── Dashboard
      ├── Profile
      └── Settings
```

> Data flows **Top → Down** (Unidirectional)

---

# 📦 2️⃣ Passing Props

> Props (properties) are used to pass data from parent to child.

---

## 🔹 Basic Example

### Parent Component

```js
function Parent() {
  return <Child name="Mihir" age={20} />;
}
```

### Child Component

```js
function Child(props) {
  return (
    <>
      <h2>Name: {props.name}</h2>
      <p>Age: {props.age}</p>
    </>
  );
}
```

---

## 🔹 Destructuring Props

```js
function Child({ name, age }) {
  return <h2>{name} - {age}</h2>;
}
```

---

## 🔹 Passing Functions as Props

```js
function Parent() {
  const greet = () => alert("Hello!");

  return <Child onGreet={greet} />;
}

function Child({ onGreet }) {
  return <button onClick={onGreet}>Greet</button>;
}
```

> Functions allow child → parent communication.

---

# 🔀 3️⃣ Conditional Rendering

> Rendering UI based on conditions.

---

## 🔹 Using if statement

```js
if (isLoggedIn) {
  return <Dashboard />;
}
return <Login />;
```

---

## 🔹 Ternary Operator

```js
{isLoggedIn ? <Dashboard /> : <Login />}
```

---

## 🔹 Logical AND (&&)

```js
{isAdmin && <AdminPanel />}
```

---

## 🔹 Switch Rendering Pattern

```js
switch(status) {
  case "loading":
    return <Loading />;
  case "success":
    return <Success />;
  default:
    return <Error />;
}
```

---

# ⬆️ 4️⃣ Lifting State Up

> When multiple children need same data, move state to their common parent.

---

## ❌ Without Lifting

Each child manages its own state → Not synchronized.

---

## ✔ With Lifting

```
Parent
 ├── Child A
 └── Child B
```

### Example

```js
function Parent() {
  const [count, setCount] = useState(0);

  return (
    <>
      <ChildA count={count} />
      <ChildB setCount={setCount} />
    </>
  );
}
```

Now:
- ChildA reads state
- ChildB updates state
- Parent controls logic

> This keeps data consistent.

---

# 🎯 5️⃣ Event Handling in React

React events use **camelCase** syntax.

---

## 🔹 Basic Event

```js
<button onClick={handleClick}>Click Me</button>
```

---

## 🔹 Event Function

```js
function handleClick() {
  console.log("Button Clicked");
}
```

---

## 🔹 Passing Parameters

```js
<button onClick={() => handleClick("Mihir")}>
  Click
</button>
```

---

## 🔹 Form Handling

```js
function Form() {
  const [value, setValue] = useState("");

  const handleSubmit = (e) => {
    e.preventDefault();
    console.log(value);
  };

  return (
    <form onSubmit={handleSubmit}>
      <input 
        value={value}
        onChange={(e) => setValue(e.target.value)}
      />
      <button type="submit">Submit</button>
    </form>
  );
}
```

---

# 🔁 Data Flow Summary

| Concept | Direction |
|----------|-----------|
| Props | Parent → Child |
| Callback Functions | Child → Parent |
| State Lifting | Shared via Parent |
| Global State | App-wide |
| Events | Trigger UI changes |

---

# ⚡ Best Practices

✔ Keep components small  
✔ Avoid prop drilling (use Context if needed)  
✔ Lift state only when necessary  
✔ Use meaningful prop names  
✔ Avoid inline heavy logic  

---

# 🔥 Common Mistakes

❌ Mutating props  
❌ Too many nested props (prop drilling)  
❌ Not lifting state properly  
❌ Using wrong key in lists  
❌ Forgetting `e.preventDefault()` in forms  

---

# 🧠 Interview Questions

- What are props?
- Difference between props & state?
- What is lifting state up?
- How child communicates with parent?
- What is conditional rendering?
- How event handling works in React?

---

# 💎 Final Thought

> Understanding props, hierarchy, and state flow is the foundation of mastering React architecture.

---

<p align="center">
  Built with ⚛️ by Mihir Patel
</p>
