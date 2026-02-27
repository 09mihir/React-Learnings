<!-- ================= HEADER ================= -->

<h1 align="center">
  📝 Formik + Yup – Complete React Form Validation Guide
</h1>

<p align="center">
  <img src="https://img.shields.io/badge/React-18+-61DAFB?style=for-the-badge&logo=react" />
  <img src="https://img.shields.io/badge/Formik-Form%20Management-2563eb?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Yup-Validation%20Schema-8b5cf6?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Forms-Production%20Ready-success?style=for-the-badge" />
</p>

---

# 🚀 What is Formik?

> Formik is a React library for building and managing forms easily.

It handles:
- Form state
- Validation
- Error messages
- Submission handling
- Touched fields

---

# 🧠 What is Yup?

> Yup is a JavaScript schema validation library.

It allows:
- Object validation
- Field validation rules
- Required checks
- Pattern matching
- Custom validation logic

Formik + Yup together = 🔥 Powerful form system

---

# 🔄 Form Handling Architecture


::contentReference[oaicite:0]{index=0}


### 🔁 Flow

1. User inputs data
2. Formik updates state
3. Yup validates schema
4. Errors shown (if any)
5. On submit → API call
6. Reset or update UI

---

# 📦 Installation

```bash
npm install formik yup
```

---

# 🎯 Basic Formik Example

```js
import { useFormik } from "formik";

function MyForm() {
  const formik = useFormik({
    initialValues: {
      email: "",
    },
    onSubmit: (values) => {
      console.log(values);
    },
  });

  return (
    <form onSubmit={formik.handleSubmit}>
      <input
        name="email"
        onChange={formik.handleChange}
        value={formik.values.email}
      />
      <button type="submit">Submit</button>
    </form>
  );
}
```

---

# 🧠 Adding Yup Validation

```js
import * as Yup from "yup";

const validationSchema = Yup.object({
  email: Yup.string()
    .email("Invalid email format")
    .required("Email is required"),
});
```

---

# 🔥 Formik + Yup Combined Example

```js
import { useFormik } from "formik";
import * as Yup from "yup";

function SignupForm() {
  const formik = useFormik({
    initialValues: {
      name: "",
      email: "",
      password: "",
    },
    validationSchema: Yup.object({
      name: Yup.string()
        .min(3, "Minimum 3 characters")
        .required("Name is required"),
      email: Yup.string()
        .email("Invalid email")
        .required("Email required"),
      password: Yup.string()
        .min(6, "Minimum 6 characters")
        .required("Password required"),
    }),
    onSubmit: (values) => {
      console.log(values);
    },
  });

  return (
    <form onSubmit={formik.handleSubmit}>
      <input
        name="name"
        onChange={formik.handleChange}
        value={formik.values.name}
      />
      {formik.errors.name && formik.touched.name && (
        <p>{formik.errors.name}</p>
      )}

      <input
        name="email"
        onChange={formik.handleChange}
        value={formik.values.email}
      />
      {formik.errors.email && formik.touched.email && (
        <p>{formik.errors.email}</p>
      )}

      <input
        type="password"
        name="password"
        onChange={formik.handleChange}
        value={formik.values.password}
      />
      {formik.errors.password && formik.touched.password && (
        <p>{formik.errors.password}</p>
      )}

      <button type="submit">Submit</button>
    </form>
  );
}
```

---

# 📦 Using `<Formik />` Component

```js
import { Formik, Form, Field, ErrorMessage } from "formik";

<Formik
  initialValues={{ email: "" }}
  validationSchema={validationSchema}
  onSubmit={(values) => console.log(values)}
>
  <Form>
    <Field name="email" />
    <ErrorMessage name="email" component="div" />
    <button type="submit">Submit</button>
  </Form>
</Formik>
```

---

# 🧠 Common Yup Validation Methods

| Method | Purpose |
|---------|----------|
| string() | Text validation |
| number() | Number validation |
| required() | Mandatory field |
| min() | Minimum length/value |
| max() | Maximum length/value |
| email() | Email validation |
| matches() | Regex validation |
| oneOf() | Confirm password |

---

# 🔐 Confirm Password Example

```js
password: Yup.string().required(),
confirmPassword: Yup.string()
  .oneOf([Yup.ref("password")], "Passwords must match")
  .required(),
```

---

# ⚡ Async Validation Example

```js
Yup.string()
  .test(
    "checkEmail",
    "Email already exists",
    async (value) => {
      const res = await fetch(`/check-email?email=${value}`);
      return res.ok;
    }
  );
```

---

# 📊 Formik vs React Hook Form

| Feature | Formik | React Hook Form |
|----------|--------|----------------|
| Easy API | Yes | Yes |
| Performance | Good | Excellent |
| Validation | Yup | Yup/Zod |
| Re-renders | More | Less |
| Learning Curve | Easy | Moderate |

---

# 🏗 Project Structure Example

```
src/
 ├── forms/
 │     ├── SignupForm.jsx
 │
 ├── validation/
 │     ├── signupSchema.js
 │
 └── App.jsx
```

---

# 🚀 Best Practices

✔ Separate validation schema  
✔ Show error only if touched  
✔ Use async validation carefully  
✔ Disable button while submitting  
✔ Reset form after success  

---

# 🔥 Common Mistakes

❌ Not handling touched state  
❌ Mixing controlled & uncontrolled inputs  
❌ Not validating confirm password  
❌ Overcomplicating validation schema  
❌ Forgetting to handle loading state  

---

# 🧠 Interview Questions

- What is Formik?
- What is Yup?
- How validation works?
- What is touched in Formik?
- Difference between controlled & uncontrolled forms?

---

# 💎 Final Thought

> Formik + Yup gives you structured, scalable, and production-ready form handling in React.

---

<p align="center">
  Built with 📝 by Mihir Patel
</p>
