<!-- ================= HEADER ================= -->

<h1 align="center">
  ⚡ TanStack (React Query) – Powerful Server State Management
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/React-18+-61DAFB?style=for-the-badge&logo=react" />
  <img src="https://img.shields.io/badge/TanStack-Query-FF4154?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Server%20State-Optimized-success?style=for-the-badge" />
</p>

---

# 🚀 What is TanStack Query?

> TanStack Query (formerly React Query) is a powerful data-fetching and server-state management library.

It helps manage:
- API calls
- Caching
- Background updates
- Refetching
- Pagination
- Mutations
- Synchronization

Perfect for:
- API-heavy apps
- Dashboards
- Real-time applications
- Complex backend-driven UIs

---

# 🧠 Client State vs Server State

| Client State | Server State |
|--------------|--------------|
| UI toggles | API data |
| Form inputs | Database data |
| Local UI logic | Remote data |
| useState / Redux | TanStack Query |

> TanStack Query manages **server state**, not UI state.

---

# 🔄 TanStack Query Lifecycle


::contentReference[oaicite:0]{index=0}


### 🔁 Flow

1. Component mounts
2. Query runs (fetch function)
3. Data cached
4. UI updates
5. Background refetch (optional)
6. Cache invalidation on mutation

---

# 📦 Installation

```bash
npm install @tanstack/react-query
```

---

# 🏗 Setup QueryClient

```js
import { QueryClient, QueryClientProvider } from "@tanstack/react-query";

const queryClient = new QueryClient();

function App() {
  return (
    <QueryClientProvider client={queryClient}>
      <YourApp />
    </QueryClientProvider>
  );
}
```

---

# 🎯 Basic useQuery Example

```js
import { useQuery } from "@tanstack/react-query";
import axios from "axios";

function fetchUsers() {
  return axios.get("/api/users").then(res => res.data);
}

function Users() {
  const { data, isLoading, error } = useQuery({
    queryKey: ["users"],
    queryFn: fetchUsers,
  });

  if (isLoading) return <p>Loading...</p>;
  if (error) return <p>Error!</p>;

  return (
    <ul>
      {data.map(user => (
        <li key={user.id}>{user.name}</li>
      ))}
    </ul>
  );
}
```

---

# 🧠 Key Concepts

| Feature | Purpose |
|----------|----------|
| queryKey | Unique identifier |
| queryFn | Fetch function |
| cache | Stores data |
| staleTime | Data freshness |
| refetch | Manual refresh |
| mutation | POST/PUT/DELETE |

---

# 🔥 useMutation Example

```js
import { useMutation, useQueryClient } from "@tanstack/react-query";

function addUser(newUser) {
  return axios.post("/api/users", newUser);
}

function AddUser() {
  const queryClient = useQueryClient();

  const mutation = useMutation({
    mutationFn: addUser,
    onSuccess: () => {
      queryClient.invalidateQueries(["users"]);
    },
  });

  return (
    <button onClick={() => mutation.mutate({ name: "Mihir" })}>
      Add User
    </button>
  );
}
```

> invalidateQueries refreshes cached data.

---

# ⚡ Caching Behavior

- Data cached automatically
- Refetch on window focus
- Background refresh
- Optimistic updates possible
- Smart revalidation

---

# 🎯 Query Options

```js
useQuery({
  queryKey: ["users"],
  queryFn: fetchUsers,
  staleTime: 5000,
  refetchOnWindowFocus: false,
});
```

---

# 📊 Pagination Example

```js
const { data } = useQuery({
  queryKey: ["users", page],
  queryFn: () => fetchUsers(page),
});
```

Query key changes → automatic refetch.

---

# 🚀 Optimistic Updates

```js
useMutation({
  mutationFn: updateUser,
  onMutate: async (newData) => {
    await queryClient.cancelQueries(["users"]);
    const previous = queryClient.getQueryData(["users"]);
    queryClient.setQueryData(["users"], old =>
      old.map(u => u.id === newData.id ? newData : u)
    );
    return { previous };
  },
});
```

Makes UI update instantly before server response.

---

# 🧠 DevTools

```bash
npm install @tanstack/react-query-devtools
```

```js
import { ReactQueryDevtools } from "@tanstack/react-query-devtools";

<ReactQueryDevtools initialIsOpen={false} />
```

---

# 📊 TanStack Query vs Axios

| Feature | Axios | TanStack Query |
|----------|--------|----------------|
| Fetch API | Yes | Uses fetch/axios |
| Caching | No | Yes |
| Background refetch | No | Yes |
| Mutation handling | Manual | Built-in |
| State management | Manual | Automatic |

---

# 🏗 Project Structure Example

```
src/
 ├── api/
 │     ├── userAPI.js
 │
 ├── hooks/
 │     ├── useUsers.js
 │
 ├── components/
 │
 └── App.jsx
```

---

# 🔥 Common Mistakes

❌ Using it for client state  
❌ Ignoring query keys  
❌ Not invalidating queries  
❌ Overfetching data  
❌ Not configuring staleTime  

---

# 🧠 Interview Questions

- What is TanStack Query?
- Difference between client & server state?
- What is queryKey?
- How caching works?
- What are mutations?
- What is optimistic update?

---

# 💎 Final Thought

> TanStack Query makes server-state management effortless and powerful.  
> Essential for modern API-driven React applications.

---

<p align="center">
  Built with ⚡ by Mihir Patel
</p>
