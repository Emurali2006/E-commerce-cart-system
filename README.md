E-COMMERCE CART SYSTEM

A simple full-stack e-commerce cart system with React frontend and Node.js backend using MongoDB.

Features

Add products to cart

Update product quantities

Remove products from cart

User authentication with registration and login

Password hashing with bcrypt

REST API with Express

MongoDB database with Mongoose

Responsive React frontend

Tech Stack

Frontend: React, CSS

Backend: Node.js, Express, MongoDB, Mongoose

Authentication: bcrypt, JWT

Setup Backend

Navigate to the backend folder:

cd backend

Install dependencies:

npm install

Create a .env file with:

PORT=5000 MONGO_URI=your_mongodb_connection_string JWT_SECRET=your_secret_key

Run the server:

npm run start

Frontend

Navigate to the frontend folder:

cd frontend

Install dependencies:

npm install

Run the app:

npm start

Usage

Access the app at http://localhost:3000

Register or login to manage your cart

Add, update, or remove products; data is handled through the backend API at http://localhost:5000/api

Example Register Component import React, { useState } from "react";

function Register() { const [form, setForm] = useState({ name: "", email: "", password: "" });

const handleChange = (e) => setForm({ ...form, [e.target.name]: e.target.value });

const handleSubmit = async (e) => { e.preventDefault(); const res = await fetch("http://localhost:5000/api/register", { method: "POST", headers: { "Content-Type": "application/json" }, body: JSON.stringify(form), }); if (res.ok) alert("Registration successful!"); else alert("Registration failed"); };

return (

Register ); }
export default Register;
