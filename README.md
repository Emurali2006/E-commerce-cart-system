# **USER AUTHENTICATION SYSTEM**

A simple full-stack user registration system with React frontend and Node.js backend using MongoDB.

---

## **FEATURES**

- User registration with name, email, and password  
- Password hashing with bcrypt  
- REST API with Express  
- MongoDB database with Mongoose  
- Responsive React signup form  

---

## **TECH STACK**

- **Frontend**: React, CSS  
- **Backend**: Node.js, Express, MongoDB, Mongoose  
- **Authentication**: bcrypt, JWT  

---

## **SETUP**

### **BACKEND**

**Install dependencies:**
```bash
cd backend
npm install
Create .env file with:

ini
Copy code
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key
Run the server:

bash
Copy code
npm start
FRONTEND
Install dependencies:

bash
Copy code
cd frontend
npm install
Run the React app:

bash
Copy code
npm start
USAGE
Visit the registration page at http://localhost:3000

Fill out and submit the form

The form sends a POST request to http://localhost:5000/api/register

EXAMPLE REGISTER COMPONENT
jsx
Copy code
import React, { useState } from "react";

function Register() {
  const [form, setForm] = useState({ name: "", email: "", password: "" });

  const handleChange = (e) =>
    setForm({ ...form, [e.target.name]: e.target.value });

  const handleSubmit = async (e) => {
    e.preventDefault();
    const res = await fetch("http://localhost:5000/api/register", {
      method: "POST",
      headers: { "Content-Type": "application/json" },
      body: JSON.stringify(form),
    });

    if (res.ok) {
      alert("Registration successful!");
    } else {
      alert("Registration failed");
    }
  };

  return (
    <form onSubmit={handleSubmit}>
      <input
        name="name"
        placeholder="Name"
        value={form.name}
        onChange={handleChange}
      />
      <input
        name="email"
        placeholder="Email"
        value={form.email}
        onChange={handleChange}
      />
      <input
        name="password"
        type="password"
        placeholder="Password"
        value={form.password}
        onChange={handleChange}
      />
      <button type="submit">Register</button>
    </form>
  );
}

export default Register;
LICENSE
This project is licensed under the MIT License.
