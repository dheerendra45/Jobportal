# Job Portal App

## Overview
This is a Full Stack Job Portal application built using the **MERN stack** (MongoDB, Express, React, Node.js) with modern authentication and monitoring solutions. The application provides a comprehensive platform for job seekers to browse and apply for jobs, and for employers to post job listings.

## 🏗️ Architecture

### Tech Stack
- **Frontend:** React.js with Vite, TailwindCSS
- **Backend:** Node.js with Express.js
- **Database:** MongoDB with Mongoose ODM
- **Authentication:** Clerk Authentication
- **Error Monitoring:** Sentry
- **Cloud Storage:** Cloudinary
- **Deployment:** Vercel

### Project Structure
```
jobPortalApp/
├── client/               # React frontend
│   ├── src/
│   │   ├── components/  # Reusable UI components
│   │   ├── pages/       # Page components
│   │   ├── context/     # React context for state management
│   │   └── assets/      # Static assets
├── server/              # Express backend
│   ├── controllers/     # Request handlers
│   ├── models/          # Database models
│   ├── routes/          # API routes
│   ├── middleware/      # Custom middleware
│   └── config/          # Configuration files
└── README.md
```

### Key Features
- 🔐 Secure user authentication with Clerk
- 📝 Job listing creation and management
- 💼 Job application system
- 📊 Real-time error monitoring with Sentry
- 🖼️ Image upload and management with Cloudinary
- 📱 Responsive design with TailwindCSS
- 🔔 Toast notifications for user feedback

---

## Client-Side

### 1. **Vite (Project Setup)**
- **Installation:**  
  `npm create vite@latest`
- **Usage:**  
  A fast build tool for modern web apps, especially React.

### 2. **React (General)**
- **Installation:**  
  `npm install`
- **Usage:**  
  Library for building UI components with a virtual DOM, creating dynamic user interfaces.

### 3. **Start Dev Server (Vite)**
- **Installation:**  
  `npm run dev`
- **Usage:**  
  Starts the development server to run the project.

### 4. **React Router DOM (Routing)**
- **Installation:**  
  `npm install react-router-dom`
- **Usage:**  
  Used to add client-side routing in a React application.

### 5. **React Toastify (Toasts / Notifications)**
- **Installation:**  
  `npm install react-toastify`
- **Usage:**  
  Library for displaying customizable toast notifications in React.

### 6. **Quill (Rich Text Editor)**
- **Installation:**  
  `npm install quill`
- **Usage:**  
  A rich text editor for web applications.

### 7. **K-Convertor**
- **Installation:**  
  `npm install k-convertor`
- **Usage:**  
  Utility for converting between different formats (specifics depend on the package version).

### 8. **Moment (Date Management)**
- **Installation:**  
  `npm install moment`
- **Usage:**  
  A date manipulation library for working with, parsing, and formatting dates and times.

### 9. **React Quill (React Integration of Quill)**
- **Installation:**  
  `npm i react-quill`
- **Usage:**  
  Integrates the Quill editor into your React components.

---

## Server-Side

### 1. **Express (Web Framework)**
- **Installation:**  
  `npm i express`
- **Usage:**  
  Minimal web application framework for Node.js.

### 2. **Json Web Token (JWT Authentication)**
- **Installation:**  
  `npm i jsonwebtoken`
- **Usage:**  
  Secure transmission of JSON objects, typically for authentication.

### 3. **Bcrypt (Password Hashing)**
- **Installation:**  
  `npm i bcrypt`
- **Usage:**  
  Used to hash passwords in Node.js for secure storage.

### 4. **Mongoose (MongoDB ORM)**
- **Installation:**  
  `npm i mongoose`
- **Usage:**  
  Manages data models and schemas in MongoDB.

### 5. **Nodemon (Auto-Restart for Development)**
- **Installation:**  
  `npm i nodemon`
- **Usage:**  
  Automatically restarts the Node.js application on changes during development.

### 6. **Svix (Webhooks)**
- **Installation:**  
  `npm i svix@1.42.0`
- **Usage:**  
  Creates and delivers webhooks securely.

### 7. **CORS (Cross-Origin Resource Sharing)**
- **Installation:**  
  `npm i cors`
- **Usage:**  
  Enables CORS in the Express app.

### 8. **Multer (File Upload Middleware)**
- **Installation:**  
  `npm i multer`
- **Usage:**  
  Handles file uploads in Node.js.

### 9. **Dotenv (Environment Variable Configuration)**
- **Installation:**  
  `npm i dotenv`
- **Usage:**  
  Loads environment variables from `.env` into `process.env`.

### 10. **Cloudinary (Cloud Storage & Media Service)**
- **Installation:**  
  `npm i cloudinary`
- **Usage:**  
  Media management platform for cloud hosting images and videos.

### 11. **Sentry (Error Monitoring)**
- **Installation:**  
  `npm install @sentry/node`
- **Usage:**  
  Monitors and tracks errors in your application.

### 12. **Sentry Profiling Node (Performance Monitoring)**
- **Installation:**  
  `npm install @sentry/profiling-node --save`
- **Usage:**  
  Tracks performance issues and monitors response times.

### 13. **Clerk for Express (Authentication Middleware)**
- **Installation:**  
  `npm install @clerk/express`
- **Usage:**  
  Handles authentication processes.

### 14. **Axios (HTTP Requests)**
- **Installation:**  
  `npm i axios`
- **Usage:**  
  Used to make HTTP requests from Node.js.

### 15. **Ngrok (Expose Local Server)**
- **Installation:**  
  `npm i ngrok`
- **Usage:**  
  Provides a secure tunnel to localhost, useful for external testing.

---

## 🚀 Getting Started

### Prerequisites
- Node.js (v14 or higher)
- MongoDB Atlas account or local MongoDB installation
- Clerk account for authentication
- Cloudinary account for image storage
- Sentry account for error monitoring (optional)

### Environment Variables

Create `.env` files in both client and server directories:

**Server `.env`:**
```env
MONGODB_URI=your_mongodb_connection_string
CLERK_WEBHOOK_SECRET=your_clerk_webhook_secret
CLOUDINARY_CLOUD_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_cloudinary_key
CLOUDINARY_API_SECRET=your_cloudinary_secret
SENTRY_DSN=your_sentry_dsn
PORT=5000
```

**Client `.env`:**
```env
VITE_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
VITE_BACKEND_URL=http://localhost:5000
```

### Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/dheerendra45/Jobportal.git
   cd Jobportal
   ```

2. **Install server dependencies:**
   ```bash
   cd server
   npm install
   ```

3. **Install client dependencies:**
   ```bash
   cd ../client
   npm install
   ```

4. **Start the development servers:**
   
   **Server:**
   ```bash
   cd server
   npm run server
   ```
   
   **Client:**
   ```bash
   cd client
   npm run dev
   ```

5. **Access the application:**
   - Frontend: `http://localhost:5173`
   - Backend: `http://localhost:5000`

---

## 📦 Deployment

### Vercel Deployment
1. Push your code to GitHub
2. Connect your repository to Vercel
3. Configure environment variables in Vercel dashboard
4. Deploy both client and server as separate services

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

---

## 📄 License

This project is open source and available under the ISC License.

---

## 👨‍💻 Author

**Dheerendra**

---

## 🙏 Acknowledgments

- Built with guidance from GreatStack
- Uses modern web development best practices
- Implements industry-standard security measures
