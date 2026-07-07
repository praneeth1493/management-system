# 🎯 Smart Event Management System

A full-stack **MERN** web application for managing events, registrations, and attendance — built with a React + Vite frontend and an Express + MongoDB backend.

---

## 🌟 Features

### 👤 User Features
- Register & login with JWT-based authentication
- Browse and search upcoming events
- Register for events
- View personal dashboard with registration history
- Track attendance records
- Update profile with photo upload

### 🛠️ Admin Features
- Admin dashboard with system-wide statistics
- Create, edit, and delete events
- Manage all user registrations
- Mark and manage attendance
- Manage user accounts

---

## 🖥️ Tech Stack

| Layer      | Technology                                      |
|------------|-------------------------------------------------|
| Frontend   | React 18, Vite, Tailwind CSS, React Router v6   |
| Backend    | Node.js, Express.js                             |
| Database   | MongoDB (Mongoose ODM)                          |
| Auth       | JSON Web Tokens (JWT), bcrypt                   |
| File Upload| Multer                                          |
| HTTP Client| Axios                                           |
| Validation | express-validator                               |

---

## 📁 Project Structure

```
management-system/
├── backend/
│   ├── config/          # Database configuration
│   ├── controllers/     # Route controllers (auth, events, users, etc.)
│   ├── middleware/      # Auth guard, error handler, file upload
│   ├── models/          # Mongoose models (User, Event, Registration, Attendance)
│   ├── routes/          # Express route definitions
│   ├── uploads/         # Uploaded images (gitignored except .gitkeep)
│   ├── utils/           # Seed data utility
│   └── server.js        # Entry point
│
└── frontend/
    ├── src/
    │   ├── components/  # Reusable UI components (Navbar, Footer, Modal, etc.)
    │   ├── context/     # React Context (AuthContext)
    │   ├── layouts/     # MainLayout wrapper
    │   ├── pages/
    │   │   ├── admin/   # Admin pages (Dashboard, ManageEvents, etc.)
    │   │   ├── public/  # Public pages (Home, Events, Login, Register)
    │   │   └── user/    # User pages (Dashboard, Profile, Attendance)
    │   ├── services/    # Axios API service modules
    │   └── utils/       # Helper utilities
    ├── index.html
    └── vite.config.js
```

---

## 🚀 Getting Started

### Prerequisites
- [Node.js](https://nodejs.org/) v18+
- [MongoDB Atlas](https://www.mongodb.com/atlas) account (or local MongoDB)
- npm or yarn

---

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/praneeth1493/management-system.git
cd management-system
```

---

### 2️⃣ Backend Setup

```bash
cd backend
npm install
```

Create a `.env` file based on the example:

```bash
cp .env.example .env
```

Fill in your values in `.env`:

```env
PORT=5000
MONGO_URI=mongodb+srv://<username>:<password>@cluster.mongodb.net/eventmanagement
JWT_SECRET=your_super_secret_jwt_key
JWT_EXPIRE=7d
NODE_ENV=development
```

Start the backend server:

```bash
# Development (with auto-restart)
npm run dev

# Production
npm start
```

> 🌐 Backend runs at `http://localhost:5000`

---

### 3️⃣ Frontend Setup

```bash
cd frontend
npm install
```

Create a `.env` file based on the example:

```bash
cp .env.example .env
```

Fill in your values in `.env`:

```env
VITE_API_URL=http://localhost:5000/api
```

Start the frontend dev server:

```bash
npm run dev
```

> 🌐 Frontend runs at `http://localhost:5173`

---

### 4️⃣ Seed Sample Data (Optional)

To populate the database with sample events and an admin user:

```bash
cd backend
npm run seed
```

---

## 🔌 API Endpoints

| Method | Endpoint                     | Description               | Auth     |
|--------|------------------------------|---------------------------|----------|
| POST   | `/api/auth/register`         | Register a new user       | Public   |
| POST   | `/api/auth/login`            | Login user                | Public   |
| GET    | `/api/auth/profile`          | Get current user profile  | Required |
| PUT    | `/api/auth/profile`          | Update profile            | Required |
| POST   | `/api/auth/logout`           | Logout user               | Public   |
| GET    | `/api/events`                | Get all events            | Public   |
| POST   | `/api/events`                | Create event              | Admin    |
| PUT    | `/api/events/:id`            | Update event              | Admin    |
| DELETE | `/api/events/:id`            | Delete event              | Admin    |
| GET    | `/api/registrations`         | Get all registrations     | Admin    |
| POST   | `/api/registrations`         | Register for event        | Required |
| GET    | `/api/attendance`            | Get attendance records    | Admin    |
| POST   | `/api/attendance`            | Mark attendance           | Admin    |
| GET    | `/api/stats`                 | Get system statistics     | Admin    |
| GET    | `/api/users`                 | Get all users             | Admin    |

---

## 🔐 Environment Variables

### Backend (`backend/.env`)

| Variable     | Description                        | Default       |
|--------------|------------------------------------|---------------|
| `PORT`       | Port for the Express server        | `5000`        |
| `MONGO_URI`  | MongoDB connection string          | —             |
| `JWT_SECRET` | Secret key for signing JWTs        | —             |
| `JWT_EXPIRE` | JWT expiry duration                | `7d`          |
| `NODE_ENV`   | Environment (`development`/`production`) | `development` |

### Frontend (`frontend/.env`)

| Variable        | Description              | Default                     |
|-----------------|--------------------------|-----------------------------|
| `VITE_API_URL`  | Backend API base URL     | `http://localhost:5000/api` |

---

## 📦 Available Scripts

### Backend
```bash
npm run dev    # Start with nodemon (hot reload)
npm start      # Start in production mode
npm run seed   # Seed sample data into the database
```

### Frontend
```bash
npm run dev      # Start Vite dev server
npm run build    # Build for production
npm run preview  # Preview production build
```

---

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin feature/your-feature`
5. Open a Pull Request

---

## 📄 License

This project is licensed under the **ISC License**.

---

<div align="center">
  Made with ❤️ by <a href="https://github.com/praneeth1493">praneeth1493</a>
</div>
