<!-- ================= HEADER ================= -->

<h1 align="center">
  🌐 Axios – Complete HTTP Client Guide for React & JavaScript
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/JavaScript-HTTP%20Client-black?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Axios-Promise%20Based-5A29E4?style=for-the-badge" />
  <img src="https://img.shields.io/badge/API-Data%20Fetching-success?style=for-the-badge" />
</p>

---

# 🚀 What is Axios?

> Axios is a promise-based HTTP client for the browser and Node.js.

It is used to:
- Make API requests
- Send & receive JSON data
- Handle authentication headers
- Intercept requests/responses
- Manage errors efficiently

Perfect for:
- React apps
- Full-stack applications
- REST APIs
- Authentication systems

---

# 🧠 Axios Request Lifecycle


::contentReference[oaicite:0]{index=0}


### 🔁 Request Flow

1. Component triggers request
2. Axios sends HTTP request
3. Server processes request
4. Server sends response
5. Axios resolves promise
6. UI updates with data

---

# 📦 Installation

```bash
npm install axios
```

---

# 🎯 Basic GET Request

```js
import axios from "axios";

axios.get("https://api.example.com/users")
  .then(response => {
    console.log(response.data);
  })
  .catch(error => {
    console.error(error);
  });
```

---

# 🔄 Using Async/Await

```js
import axios from "axios";

async function fetchUsers() {
  try {
    const response = await axios.get("/api/users");
    console.log(response.data);
  } catch (error) {
    console.error(error);
  }
}
```

---

# 📤 POST Request

```js
axios.post("/api/users", {
  name: "Mihir",
  email: "mihir@example.com"
});
```

---

# 📥 PUT & DELETE Requests

```js
// PUT
axios.put("/api/users/1", { name: "Updated Name" });

// DELETE
axios.delete("/api/users/1");
```

---

# 🧾 Axios Response Structure

```js
{
  data: {},
  status: 200,
  statusText: "OK",
  headers: {},
  config: {}
}
```

Most important → `response.data`

---

# ⚡ Creating Axios Instance (Best Practice)

```js
import axios from "axios";

const api = axios.create({
  baseURL: "https://api.example.com",
  timeout: 5000,
  headers: {
    "Content-Type": "application/json",
  },
});

export default api;
```

Now use:

```js
api.get("/users");
```

---

# 🔐 Sending Headers (Auth Token)

```js
axios.get("/api/profile", {
  headers: {
    Authorization: `Bearer ${token}`,
  },
});
```

---

# 🧠 Interceptors (Advanced)

## Request Interceptor

```js
api.interceptors.request.use((config) => {
  config.headers.Authorization = `Bearer ${token}`;
  return config;
});
```

## Response Interceptor

```js
api.interceptors.response.use(
  (response) => response,
  (error) => {
    if (error.response.status === 401) {
      console.log("Unauthorized");
    }
    return Promise.reject(error);
  }
);
```

Used for:
- Auto token attach
- Global error handling
- Logging

---

# ⚛️ Axios in React (useEffect Example)

```js
import { useEffect, useState } from "react";
import axios from "axios";

function Users() {
  const [users, setUsers] = useState([]);

  useEffect(() => {
    axios.get("/api/users")
      .then(res => setUsers(res.data))
      .catch(err => console.error(err));
  }, []);

  return (
    <ul>
      {users.map(user => (
        <li key={user.id}>{user.name}</li>
      ))}
    </ul>
  );
}
```

---

# 🌍 Handling Errors

```js
try {
  const res = await axios.get("/api/data");
} catch (error) {
  if (error.response) {
    console.log(error.response.status);
  } else if (error.request) {
    console.log("No response received");
  } else {
    console.log("Request error");
  }
}
```

---

# 📊 Axios vs Fetch API

| Feature | Axios | Fetch |
|----------|--------|--------|
| JSON auto transform | Yes | No |
| Interceptors | Yes | No |
| Timeout support | Yes | Manual |
| Simpler syntax | Yes | Moderate |
| Error handling | Better | Manual |

---

# 🏗 Project Structure Example

```
src/
 ├── api/
 │     ├── axiosInstance.js
 │     ├── userService.js
 │
 ├── components/
 │
 └── App.jsx
```

---

# 🚀 Best Practices

✔ Create axios instance  
✔ Use interceptors for auth  
✔ Handle loading & error states  
✔ Avoid calling API in render  
✔ Use async/await for readability  

---

# 🔥 Common Mistakes

❌ Not handling errors  
❌ Hardcoding base URLs everywhere  
❌ Ignoring loading states  
❌ Making multiple unnecessary requests  
❌ Not cancelling requests on unmount  

---

# 🧠 Interview Questions

- What is Axios?
- Difference between Axios & Fetch?
- What are interceptors?
- How to handle authentication?
- How to cancel requests?

---

# 💎 Final Thought

> Axios simplifies API communication with clean syntax and powerful features.  
> Essential tool for modern React & full-stack applications.

---

<p align="center">
  Built with 🌐 by Mihir Patel
</p>
