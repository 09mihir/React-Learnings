<!-- ================= HEADER ================= -->

<h1 align="center">
  ⚛️ React + Redux Toolkit – Advanced Developer Guide
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/React-18+-61DAFB?style=for-the-badge&logo=react" />
  <img src="https://img.shields.io/badge/Redux%20Toolkit-Official%20Redux%20Way-764ABC?style=for-the-badge&logo=redux" />
  <img src="https://img.shields.io/badge/RTK%20Query-Data%20Fetching-ff9800?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Level-Production%20Ready-success?style=for-the-badge" />
</p>

---

# 🚀 What is Redux Toolkit?

> Redux Toolkit (RTK) is the official, recommended way to write Redux logic.

It simplifies:
- Store configuration
- Reducer creation
- Immutable updates
- Async logic handling
- API data fetching (RTK Query)

---

# 🏗 Redux Toolkit Architecture

## 🔁 Standard Redux Flow


::contentReference[oaicite:0]{index=0}


### Flow Explanation

1. UI dispatches an **Action**
2. Action goes to **Slice Reducer**
3. Reducer updates **Store**
4. Store notifies subscribed UI
5. UI re-renders with updated state

> Redux follows Unidirectional Data Flow

---

# 🧠 Advanced Architecture (With Async & RTK Query)


::contentReference[oaicite:1]{index=1}


### Extended Flow

UI → dispatch →  
• Slice Reducer (sync state)  
• createAsyncThunk (async logic)  
• RTK Query (API layer)  

→ Store updates → UI re-renders  

---

# 📦 Installation

```bash
npm install @reduxjs/toolkit react-redux
```

---

# 📁 Production Folder Structure

```
src/
 ├── app/
 │    └── store.js
 ├── features/
 │    ├── counter/
 │    │     ├── counterSlice.js
 │    │
 │    ├── users/
 │    │     ├── usersSlice.js
 │    │     └── usersAPI.js
 │
 ├── services/
 │    └── api.js   (RTK Query setup)
 │
 ├── components/
 └── main.jsx
```

---

# 🏪 Store Configuration

```js
// app/store.js

import { configureStore } from "@reduxjs/toolkit";
import counterReducer from "../features/counter/counterSlice";
import { api } from "../services/api";

export const store = configureStore({
  reducer: {
    counter: counterReducer,
    [api.reducerPath]: api.reducer,
  },
  middleware: (getDefaultMiddleware) =>
    getDefaultMiddleware().concat(api.middleware),
});
```

---

# 🔹 Creating a Slice

```js
import { createSlice } from "@reduxjs/toolkit";

const initialState = {
  value: 0,
};

const counterSlice = createSlice({
  name: "counter",
  initialState,
  reducers: {
    increment: (state) => {
      state.value += 1;
    },
    decrement: (state) => {
      state.value -= 1;
    },
    incrementByAmount: (state, action) => {
      state.value += action.payload;
    },
  },
});

export const { increment, decrement, incrementByAmount } =
  counterSlice.actions;

export default counterSlice.reducer;
```

> RTK uses Immer internally — safe mutation allowed.

---

# 🌍 Async Logic – createAsyncThunk

```js
import { createAsyncThunk } from "@reduxjs/toolkit";

export const fetchUsers = createAsyncThunk(
  "users/fetchUsers",
  async () => {
    const response = await fetch("/api/users");
    return response.json();
  }
);
```

### Handling in Slice

```js
extraReducers: (builder) => {
  builder
    .addCase(fetchUsers.pending, (state) => {
      state.status = "loading";
    })
    .addCase(fetchUsers.fulfilled, (state, action) => {
      state.status = "succeeded";
      state.users = action.payload;
    })
    .addCase(fetchUsers.rejected, (state) => {
      state.status = "failed";
    });
}
```

---

# ⚡ RTK Query (Advanced API Handling)

RTK Query is built-in powerful data fetching & caching tool.

---

## 🔧 Creating API Service

```js
// services/api.js

import { createApi, fetchBaseQuery } from "@reduxjs/toolkit/query/react";

export const api = createApi({
  reducerPath: "api",
  baseQuery: fetchBaseQuery({ baseUrl: "/api" }),
  endpoints: (builder) => ({
    getUsers: builder.query({
      query: () => "/users",
    }),
  }),
});

export const { useGetUsersQuery } = api;
```

---

## 🎯 Using RTK Query in Component

```js
function Users() {
  const { data, error, isLoading } = useGetUsersQuery();

  if (isLoading) return <p>Loading...</p>;
  if (error) return <p>Error</p>;

  return (
    <ul>
      {data.map((user) => (
        <li key={user.id}>{user.name}</li>
      ))}
    </ul>
  );
}
```

---

# 📊 Redux Toolkit vs Traditional Redux

| Traditional Redux | Redux Toolkit |
|------------------|--------------|
| Manual setup | configureStore |
| Action types manually written | Auto generated |
| Manual immutable updates | Immer |
| Complex async setup | createAsyncThunk |
| No built-in API layer | RTK Query |

---

# 🧠 Core APIs Summary

| API | Purpose |
|------|----------|
| configureStore | Create store |
| createSlice | Reducer + Actions |
| createAsyncThunk | Async logic |
| createApi | API layer |
| fetchBaseQuery | Base API handler |

---

# 🏆 Best Practices

✔ Feature-based structure  
✔ Keep slices small  
✔ Use RTK Query for API-heavy apps  
✔ Avoid unnecessary global state  
✔ Normalize large datasets  

---

# 🎯 When to Use Redux Toolkit?

Use when:
- Large applications
- Shared state across many components
- Complex business logic
- API-heavy dashboards

Avoid when:
- Small apps
- Simple local component state

---

# 💎 Final Thought

> Redux Toolkit makes state management scalable, readable, and production-ready.

---

<p align="center">
  Built with ⚛️ by Mihir Patel
</p>
