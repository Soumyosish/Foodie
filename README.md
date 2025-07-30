# 🍴 Foodie — Full-Stack Restaurant App

A full-stack web application for browsing, listing, and managing a variety of food items. Built using React (Frontend), Express.js (Backend), and MongoDB, with complete Docker support for seamless development and deployment.

![Foodie Homepage](images/foodie-home-light.png)
<sup>Homepage – Light Mode</sup>

---

## 📑 Table of Contents

- [🔧 Tech Stack](#-tech-stack)
  - [🖥️ Frontend](#️-frontend)
  - [🌐 Backend](#-backend)
  - [🗄️ Database](#️-database)
- [✨ Key Features](#-key-features)
- [🚀 Getting Started](#-getting-started)
  - [Prerequisites](#prerequisites)
  - [🐳 Docker Setup (Recommended)](#-docker-setup-recommended)
  - [📦 Manual Installation](#-manual-installation)
  - [🔧 Development Setup](#-development-setup)
  - [⚙️ Environment Variables](#-environment-variables)
- [📁 Project Structure](#-project-structure)
- [🐳 Docker Commands](#-docker-commands)
- [🧪 Linting](#-linting)
- [🧰 Scripts](#-scripts)
- [📝 Notes](#-notes)
- [🤝 Contributing](#-contributing)
- [📄 License](#-license)
- [🙌 Acknowledgements](#-acknowledgements)

---

## 🔧 Tech Stack

### 🖥️ Frontend

- **React 18.3**
- **Vite** (fast development tooling)
- **React Router DOM** (routing)
- **GSAP** (animations)
- **ESLint** (linting)

### 🌐 Backend

- **Node.js + Express**
- **MongoDB** with **Mongoose**
- **CORS + JSON Middleware**
- **dotenv** (environment management)
- **Razorpay** (payment gateway)
- **Multer** (file uploads)
- **Modular API Routing**

### 🗄️ Database

- **MongoDB** (NoSQL data storage)

### 🐳 DevOps

- **Docker** (Containerization)
- **Docker Compose** (Multi-service orchestration)

---

## ✨ Key Features

- 🥗 **Explore a variety of dishes**
- 🛒 **Add to cart, checkout, and order**
- 🖤 **Wishlist and user auth**
- 🌗 **Light/Dark mode toggle**
- 💳 **Online payment with Razorpay**
- 📱 **Mobile-friendly responsive UI**

---

## 🚀 Getting Started

### Prerequisites

#### Docker Setup (Recommended)

- Docker Desktop
- Docker Compose

#### Manual Setup

- Node.js (v16 or above)
- npm or yarn
- MongoDB (local or cloud)

---

### 🐳 Docker Setup (Recommended)

**One-command setup for the entire application:**

```bash
# Clone the repository
git clone https://github.com/your-username/foodie.git
cd foodie

# Start all services with Docker
docker-compose up --build
```

**Access the application:**
- 🌐 **Frontend**: http://localhost:3000
- 🛠️ **Admin Panel**: http://localhost:5173
- 🔌 **Backend API**: http://localhost:4000
- 🗄️ **MongoDB**: localhost:27017

**Docker Services:**
- **foodie-frontend**: React app (Port 3000)
- **foodie-admin**: Admin panel (Port 5173)
- **foodie-backend**: Express API (Port 4000)
- **foodie-mongodb**: MongoDB database (Port 27017)

---

### 📦 Manual Installation

```bash
# Clone the repository
git clone https://github.com/your-username/foodie.git
cd foodie
```

---

#### Frontend

```bash
cd frontend
npm install
npm install gsap
npm run dev
```

---

#### Backend

```bash
cd backend 
npm install
npm install dotenv
```

---

#### Admin

```bash
cd admin
npm install
```

---
### 🔧 Development Setup

#### Docker Development
```bash
# Start all services
docker-compose up

# Start in detached mode
docker-compose up -d

# View logs for specific service
docker-compose logs frontend
docker-compose logs backend
docker-compose logs admin
```

#### Manual Development

**Start Frontend:**
```bash
cd frontend
npm run dev
```

**Start Admin Panel:**
```bash
cd admin
npm run dev
```

**Start Backend:**
```bash
cd backend
npm run server
```

**Start MongoDB:**
```bash
# Make sure MongoDB is running locally
mongod
```

---

### Environment Variables
The application uses the following environment variables:

**Backend:**
- `MONGODB_URI`: MongoDB connection string
- `JWT_SECRET`: Secret key for JWT tokens
- `PORT`: Server port (default: 4000)

**Frontend:**
- `REACT_APP_API_URL`: Backend API URL

**Admin:**
- `VITE_API_URL`: Backend API URL for Vite

---

## 📁 Project Structure

```
Foodie/
├── frontend/                 # React frontend application
│   ├── src/
│   ├── Dockerfile
│   ├── .dockerignore
│   └── package.json
├── backend/                  # Express.js backend API
│   ├── routes/
│   ├── config/
│   ├── uploads/
│   ├── server.js
│   ├── Dockerfile
│   ├── .dockerignore
│   └── package.json
├── admin/                    # React admin panel
│   ├── src/
│   ├── Dockerfile
│   ├── .dockerignore
│   └── package.json
├── docker-compose.yml        # Multi-service orchestration
├── .dockerignore            # Root Docker ignore file
├── README.md
└── CONTRIBUTING.md
```

---

## 🐳 Docker Commands

### Basic Operations
```bash
# Build and start all services
docker-compose up --build

# Start services in background
docker-compose up -d

# Stop all services
docker-compose down

# Stop and remove volumes (⚠️ deletes database data)
docker-compose down -v

# Restart specific service
docker-compose restart backend

# View running containers
docker-compose ps
```

### Development Commands
```bash
# View logs for all services
docker-compose logs

# View logs for specific service
docker-compose logs -f frontend

# Execute commands in running container
docker-compose exec backend npm install new-package

# Rebuild specific service
docker-compose build backend
```

### Database Management
```bash
# Access MongoDB shell
docker-compose exec mongodb mongosh

# Backup database
docker-compose exec mongodb mongodump --out /backup

# View MongoDB logs
docker-compose logs mongodb
```

---
## 🧪 Linting

ESLint is pre-configured for React and Hooks.

```bash
# Frontend linting
cd frontend && npm run lint

# Admin linting
cd admin && npm run lint
```

---

## 🧰 Scripts

### Frontend & Admin Scripts
| Command        | Description                  |
|----------------|------------------------------|
| `npm run dev`  | Start Vite development server |
| `npm run build`| Build for production |
| `npm run preview` | Preview production build    |
| `npm run lint` | Run ESLint checks             |

### Backend Scripts
| Command        | Description                  |
|----------------|------------------------------|
| `npm start`    | Start production server      |
| `npm run server` | Start development server with nodemon |

---

## 📝 Notes

### Database Configuration
- **Docker**: MongoDB runs automatically with authentication
  - Username: `admin`
  - Password: `password123`
  - Database: `foodie`
- **Manual**: Update `connectDB()` in `backend/config/db.js`

### File Uploads
- Backend handles file uploads via Multer
- Files are stored in `backend/uploads/` directory
- Docker setup includes volume mounting for persistence

---

## 🤝 Contributing

We welcome contributions to the Foodie project! If you find this project helpful, please consider:

- ⭐ **Star this repository** to show your support and help others discover it
- 🐛 Report bugs or suggest features through issues
- 🔧 Submit pull requests for improvements
- 📖 Help improve documentation
- 🚀 For more info go to [CONTRIBUTING.md](CONTRIBUTING.md)

### Development Workflow
1. Fork the repository
2. Create a feature branch
3. Use Docker for consistent development environment
4. Test your changes with `docker-compose up --build`
5. Submit a pull request

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 🙌 Acknowledgements

- [React](https://reactjs.org/)
- [Vite](https://vitejs.dev/)
- [Express](https://expressjs.com/)
- [MongoDB](https://www.mongodb.com/)
- [Docker](https://www.docker.com/)

