# Vehicle Rent Server

**Live Deployment:** [https://rentserver-murex.vercel.app/](https://rentserver-murex.vercel.app/)

---

## 📌 Project Description

The **Vehicle Rent Server** is a complete backend solution for managing a vehicle rental service. It is built using **Node.js, Express.js, PostgreSQL, and TypeScript**. The system allows users to create accounts, log in, browse available vehicles, and make bookings.

Admins have additional privileges to manage vehicles, users, and bookings. The system automatically tracks vehicle availability to ensure a smooth and organized rental process.

---

## ✨ Features

* User account system with **signup & login**
* **Role-based access control** (Admin & Customer)
* Complete **vehicle management** (add, update, delete, view)
* **Booking system** with create & cancel options
* Admin can mark vehicles as **returned**
* **Automatic handling of expired bookings**
* Proper input validation with clear error responses
* **Real-time availability tracking** for vehicles
* PostgreSQL database with a solid relational structure

---

## 🛠 Technology Stack

* **Node.js**
* **Express.js**
* **TypeScript**
* **PostgreSQL**
* **JWT Authentication**
* **bcrypt.js**
* **Neon Database**
* **Postman**

---

## ⚙️ Setup & Usage

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/naim-rahman/Rent-Server-B6A2-
```

### 2️⃣ Install Dependencies

```bash
npm install
```

### 3️⃣ Configure Environment Variables

Create a `.env` file in the root directory:

```env
PORT=5000
CONNECTION_STRING=<PostgreSQL_Connection_String>
SECRET_JWT=<Secret_JWT_Key>
```

### 4️⃣ Run the Project

```bash
npm run dev
```

The server will start at:

```
http://localhost:5000
```

---

## 🔗 API Endpoints

### 🔐 Authentication

* **Signup:** `POST /api/v1/auth/signup`
  Register a new user account

* **Signin:** `POST /api/v1/auth/signin`
  Login and receive a JWT token

---

### 👤 Users

* **Get All Users:** `GET /api/v1/users`
  Admin can view all users

* **Update User:** `PUT /api/v1/users/:id`
  Admin can update any user | Customer can update their own profile

* **Delete User:** `DELETE /api/v1/users/:id`
  Admin can delete a user (only if no active bookings exist)

---

### 🚙 Vehicles

* **Create Vehicle:** `POST /api/v1/vehicles`
  Admin adds a new vehicle (name, type, registration, daily rent price, availability)

* **Get All Vehicles:** `GET /api/v1/vehicles`
  Public view of all vehicles

* **Get Single Vehicle:** `GET /api/v1/vehicles/:id`
  View specific vehicle details

* **Update Vehicle:** `PUT /api/v1/vehicles/:id`
  Admin updates vehicle details or availability

* **Delete Vehicle:** `DELETE /api/v1/vehicles/:id`
  Admin deletes vehicle (only if no active bookings exist)

---

### 📅 Bookings

* **Create Booking:** `POST /api/v1/bookings`
  Admin & Customer can create bookings

  * Validates vehicle availability
  * Calculates total price (daily rate × duration)
  * Updates vehicle status to **booked**

* **Get All Bookings:** `GET /api/v1/bookings`
  Admin: View all bookings
  Customer: View own bookings only

* **Update Booking:** `PUT /api/v1/bookings/:id`
  Customer: Cancel booking (before start date only)
  Admin: Mark booking as **returned** (vehicle becomes available)

* **Auto Return Bookings:** `PUT /api/v1/bookings/auto-return`
  Admin-only endpoint to auto-return expired bookings

---

* **GitHub Repository:** [https://github.com/naim-rahman/Rent-Server-B6A2-](https://github.com/naim-rahman/Rent-Server-B6A2-)
* **Live Deployment:** [https://rentserver-murex.vercel.app/](https://rentserver-murex.vercel.app/)

