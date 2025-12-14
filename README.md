# 🚀 Job Portal App

<div align="center">

![MERN Stack](https://img.shields.io/badge/MERN-Stack-success?style=for-the-badge)
![React](https://img.shields.io/badge/React-18.3.1-61DAFB?style=for-the-badge&logo=react)
![Node.js](https://img.shields.io/badge/Node.js-Express-339933?style=for-the-badge&logo=node.js)
![MongoDB](https://img.shields.io/badge/MongoDB-Mongoose-47A248?style=for-the-badge&logo=mongodb)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-4.1.6-06B6D4?style=for-the-badge&logo=tailwindcss)

A modern, full-stack job portal application that connects job seekers with employers through a seamless, secure, and feature-rich platform.

[Features](#-features) • [Architecture](#️-architecture) • [Getting Started](#-getting-started) • [API Documentation](#-api-endpoints) • [Deployment](#-deployment)

</div>

---

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#-features)
- [Architecture](#️-architecture)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [API Endpoints](#-api-endpoints)
- [Database Schema](#-database-schema)
- [Deployment](#-deployment)
- [Contributing](#-contributing)

---

## Overview

A comprehensive **Full Stack Job Portal** built with the **MERN stack** (MongoDB, Express, React, Node.js), featuring modern authentication, cloud storage, real-time error monitoring, and a beautiful responsive UI. This platform serves two primary user roles:

- **Job Seekers**: Browse jobs, apply with resume uploads, and track application status
- **Recruiters/Companies**: Post jobs, manage listings, review applications, and control visibility

---

## ✨ Features

### 👤 For Job Seekers

- **🔍 Smart Job Search**: Browse and filter jobs by category, location, and level
- **📄 Easy Applications**: Apply to jobs with resume upload functionality
- **📊 Application Tracking**: Monitor all submitted applications and their status
- **👨‍💼 Profile Management**: Update resume and personal information
- **🔐 Secure Authentication**: Login via Clerk with OAuth support
- **📱 Responsive Design**: Seamless experience across all devices

### 🏢 For Recruiters/Companies

- **📝 Job Posting**: Create and publish job listings with rich text descriptions
- **🖼️ Company Branding**: Upload company logos via Cloudinary
- **👥 Application Management**: View and manage all job applications
- **✅ Status Control**: Update application status (Pending, Accepted, Rejected)
- **👁️ Visibility Toggle**: Show/hide job postings dynamically
- **📈 Dashboard Analytics**: Track posted jobs and applicant statistics
- **🔒 Secure Authentication**: JWT-based company login with bcrypt password hashing

### 🛠️ Technical Features

- **⚡ Real-time Notifications**: Toast notifications for user actions
- **🎨 Rich Text Editor**: Quill-powered job description editor
- **☁️ Cloud Storage**: Cloudinary integration for image and resume uploads
- **📊 Error Monitoring**: Sentry integration for tracking and debugging errors
- **🔄 Webhook Integration**: Clerk webhooks for user synchronization
- **🔐 Middleware Protection**: Role-based route protection
- **⚙️ File Upload**: Multer middleware for handling multipart/form-data
- **🌐 CORS Enabled**: Cross-origin resource sharing for API access

---

## 🏗️ Architecture

### System Design

```
┌─────────────────────────────────────────────────────────────┐
│                     CLIENT (React + Vite)                    │
├─────────────────────────────────────────────────────────────┤
│  Components  │  Pages  │  Context API  │  React Router DOM  │
│  TailwindCSS │  Quill  │  Axios        │  Clerk Auth        │
└──────────────────────┬──────────────────────────────────────┘
                       │ HTTP/REST API
                       ▼
┌─────────────────────────────────────────────────────────────┐
│                  SERVER (Node.js + Express)                  │
├─────────────────────────────────────────────────────────────┤
│  Routes  │  Controllers  │  Middleware  │  Models (Mongoose)│
│  JWT     │  Multer       │  Bcrypt      │  Clerk SDK        │
└──────────────────────┬──────────────────────────────────────┘
                       │
        ┌──────────────┼──────────────┐
        ▼              ▼              ▼
   ┌─────────┐   ┌──────────┐   ┌─────────┐
   │ MongoDB │   │Cloudinary│   │  Sentry │
   │ Atlas   │   │  (CDN)   │   │(Logging)│
   └─────────┘   └──────────┘   └─────────┘
```

### Application Flow

#### Job Seeker Flow

```
User Login (Clerk) → Browse Jobs → View Job Details → Apply with Resume →
Track Applications → Receive Status Updates
```

#### Recruiter Flow

```
Company Register → Login (JWT) → Post Job → Manage Listings →
View Applications → Update Status → Toggle Visibility
```

### Authentication Architecture

- **Job Seekers**: Clerk-based OAuth authentication (Google, GitHub, Email)
- **Recruiters**: Traditional JWT authentication with bcrypt password hashing
- **Protected Routes**: Middleware-based authorization for role-specific access
- **Webhooks**: Clerk webhooks sync user data to MongoDB

---

## 💻 Tech Stack

### Frontend

| Technology           | Version | Purpose                                            |
| -------------------- | ------- | -------------------------------------------------- |
| **React**            | 18.3.1  | UI library for building component-based interfaces |
| **Vite**             | 6.0.5   | Lightning-fast build tool and dev server           |
| **TailwindCSS**      | 4.1.6   | Utility-first CSS framework for styling            |
| **React Router DOM** | 7.6.0   | Client-side routing and navigation                 |
| **Clerk React**      | 5.31.2  | User authentication and management                 |
| **Axios**            | 1.9.0   | HTTP client for API requests                       |
| **React Quill**      | 2.0.0   | Rich text editor for job descriptions              |
| **React Toastify**   | 11.0.5  | Toast notifications for user feedback              |
| **Moment.js**        | 2.30.1  | Date parsing and formatting                        |
| **K-Convert**        | 1.0.6   | Number formatting (e.g., 50000 → 50K)              |

### Backend

| Technology        | Version | Purpose                              |
| ----------------- | ------- | ------------------------------------ |
| **Node.js**       | Latest  | JavaScript runtime environment       |
| **Express.js**    | 4.21.2  | Web application framework            |
| **MongoDB**       | Latest  | NoSQL database for data persistence  |
| **Mongoose**      | 8.9.5   | MongoDB ODM for schema modeling      |
| **JWT**           | 9.0.2   | JSON Web Tokens for authentication   |
| **Bcrypt**        | 5.1.1   | Password hashing for security        |
| **Clerk Express** | 1.4.19  | Express middleware for Clerk         |
| **Cloudinary**    | 2.5.1   | Cloud storage for images and resumes |
| **Multer**        | 1.4.5   | Multipart form-data handling         |
| **Sentry**        | 8.55.0  | Error tracking and monitoring        |
| **CORS**          | 2.8.5   | Cross-origin resource sharing        |
| **Svix**          | 1.42.0  | Webhook validation and processing    |

### DevOps & Deployment

- **Vercel**: Serverless deployment platform
- **MongoDB Atlas**: Cloud database hosting
- **Cloudinary CDN**: Asset delivery network
- **Sentry**: Real-time error monitoring
- **Nodemon**: Development auto-restart

---

## 📁 Project Structure

```
jobPortalApp/
│
├── client/                          # Frontend React Application
│   ├── public/                      # Static assets
│   ├── src/
│   │   ├── assets/                  # Images, icons, and asset files
│   │   │   └── assets.js            # Asset exports
│   │   ├── components/              # Reusable UI components
│   │   │   ├── AppDownload.jsx      # App download CTA section
│   │   │   ├── Footer.jsx           # Footer component
│   │   │   ├── Hero.jsx             # Landing page hero section
│   │   │   ├── JobCard.jsx          # Individual job card component
│   │   │   ├── JobListing.jsx       # Job list display
│   │   │   ├── Loading.jsx          # Loading spinner component
│   │   │   ├── Navbar.jsx           # Navigation bar
│   │   │   └── RecruiterLogin.jsx   # Recruiter login modal
│   │   ├── context/
│   │   │   └── AppContext.jsx       # Global state management
│   │   ├── pages/                   # Route-based page components
│   │   │   ├── Home.jsx             # Landing page
│   │   │   ├── ApplyJob.jsx         # Job application page
│   │   │   ├── Applications.jsx     # User applications list
│   │   │   ├── Dashboard.jsx        # Recruiter dashboard
│   │   │   ├── AddJob.jsx           # Job creation form
│   │   │   ├── ManageJobs.jsx       # Job management interface
│   │   │   └── ViewApplications.jsx # Application review page
│   │   ├── App.jsx                  # Main app component with routing
│   │   ├── main.jsx                 # React entry point
│   │   └── index.css                # Global styles
│   ├── eslint.config.js             # ESLint configuration
│   ├── tailwind.config.js           # Tailwind CSS configuration
│   ├── vite.config.js               # Vite build configuration
│   ├── vercel.json                  # Vercel deployment config
│   └── package.json                 # Frontend dependencies
│
├── server/                          # Backend Node.js Application
│   ├── config/
│   │   ├── db.js                    # MongoDB connection setup
│   │   ├── cloudinary.js            # Cloudinary configuration
│   │   ├── multer.js                # File upload configuration
│   │   └── instrument.js            # Sentry instrumentation
│   ├── controllers/
│   │   ├── companyController.js     # Company/recruiter logic
│   │   ├── jobController.js         # Job CRUD operations
│   │   ├── userController.js        # User/applicant logic
│   │   └── webhooks.js              # Clerk webhook handlers
│   ├── models/
│   │   ├── Company.js               # Company schema
│   │   ├── Job.js                   # Job schema
│   │   ├── JobApplication.js        # Application schema
│   │   └── User.js                  # User schema
│   ├── routes/
│   │   ├── companyRoutes.js         # Company API endpoints
│   │   ├── jobRoutes.js             # Job API endpoints
│   │   └── userRoutes.js            # User API endpoints
│   ├── middleware/
│   │   └── authMiddleware.js        # JWT authentication middleware
│   ├── utils/
│   │   └── generateToken.js         # JWT token generation utility
│   ├── server.js                    # Express server entry point
│   ├── vercel.json                  # Vercel serverless config
│   └── package.json                 # Backend dependencies
│
├── package.json                     # Root workspace configuration
└── README.md                        # Project documentation
```

---

## 🚀 Getting Started

### Prerequisites

Before you begin, ensure you have the following installed and set up:

- **Node.js** (v14 or higher) - [Download](https://nodejs.org/)
- **npm** or **yarn** - Package manager
- **MongoDB Atlas Account** - [Sign Up](https://www.mongodb.com/cloud/atlas)
- **Clerk Account** - [Sign Up](https://clerk.com/)
- **Cloudinary Account** - [Sign Up](https://cloudinary.com/)
- **Sentry Account** (Optional) - [Sign Up](https://sentry.io/)

---

### Installation Steps

#### 1. Clone the Repository

```bash
git clone https://github.com/dheerendra45/jobportal.git
cd jobportal
```

#### 2. Server Setup

```bash
cd server
npm install
```

Create a `.env` file in the `server` directory:

```env
# MongoDB Configuration
MONGODB_URI=your_mongodb_connection_string

# Clerk Authentication
CLERK_WEBHOOK_SECRET=your_clerk_webhook_secret

# Cloudinary Configuration
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret

# Sentry Error Monitoring (Optional)
SENTRY_DSN=your_sentry_dsn

# Server Configuration
PORT=5000
```

#### 3. Client Setup

```bash
cd ../client
npm install
```

Create a `.env` file in the `client` directory:

```env
# Clerk Authentication
VITE_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key

# Backend API URL
VITE_BACKEND_URL=http://localhost:5000
```

#### 4. Start Development Servers

**Terminal 1 - Backend Server:**

```bash
cd server
npm run server
```

**Terminal 2 - Frontend Development Server:**

```bash
cd client
npm run dev
```

#### 5. Access the Application

- **Frontend**: [http://localhost:5173](http://localhost:5173)
- **Backend API**: [http://localhost:5000](http://localhost:5000)

---

### Environment Variables Explanation

| Variable                | Description                  | Where to Get                                          |
| ----------------------- | ---------------------------- | ----------------------------------------------------- |
| `MONGODB_URI`           | MongoDB connection string    | MongoDB Atlas Dashboard → Connect → Connection String |
| `CLERK_WEBHOOK_SECRET`  | Clerk webhook signing secret | Clerk Dashboard → Webhooks → Add Endpoint             |
| `CLERK_PUBLISHABLE_KEY` | Clerk frontend API key       | Clerk Dashboard → API Keys                            |
| `CLOUDINARY_CLOUD_NAME` | Cloudinary cloud name        | Cloudinary Dashboard → Account Details                |
| `CLOUDINARY_API_KEY`    | Cloudinary API key           | Cloudinary Dashboard → Settings → API Keys            |
| `CLOUDINARY_API_SECRET` | Cloudinary API secret        | Cloudinary Dashboard → Settings → API Keys            |
| `SENTRY_DSN`            | Sentry project DSN           | Sentry Dashboard → Settings → Client Keys (DSN)       |

---

## 🔌 API Endpoints

### Public Endpoints

#### Jobs

```http
GET    /api/jobs              # Get all visible jobs
GET    /api/jobs/:id          # Get job by ID
```

### User Endpoints (Clerk Protected)

#### User Profile

```http
GET    /api/users/user        # Get current user data
POST   /api/users/update-resume  # Upload/update resume
```

#### Job Applications

```http
POST   /api/users/apply       # Apply for a job
GET    /api/users/applications # Get user's applications
```

### Company Endpoints (JWT Protected)

#### Authentication

```http
POST   /api/company/register  # Register new company (multipart/form-data)
POST   /api/company/login     # Company login
```

#### Company Profile

```http
GET    /api/company/company   # Get company data
```

#### Job Management

```http
POST   /api/company/post-job  # Create new job posting
GET    /api/company/list-job  # Get company's posted jobs
POST   /api/company/change-visiblity  # Toggle job visibility
```

#### Application Management

```http
GET    /api/company/applicants       # Get all applicants for company jobs
POST   /api/company/change-status    # Update application status
```

### Webhook Endpoints

```http
POST   /webhooks              # Clerk user webhook
```

---

### Request/Response Examples

#### Apply for Job

**Request:**

```http
POST /api/users/apply
Content-Type: application/json
Authorization: Bearer <clerk-token>

{
  "jobId": "507f1f77bcf86cd799439011"
}
```

**Response:**

```json
{
  "success": true,
  "message": "Application submitted successfully",
  "application": {
    "_id": "507f1f77bcf86cd799439012",
    "jobId": "507f1f77bcf86cd799439011",
    "userId": "user_2abc123",
    "status": "Pending",
    "date": 1702569600000
  }
}
```

#### Post a Job

**Request:**

```http
POST /api/company/post-job
Content-Type: application/json
Authorization: Bearer <jwt-token>

{
  "title": "Senior Full Stack Developer",
  "description": "<p>We are looking for...</p>",
  "location": "Remote",
  "category": "Programming",
  "level": "Senior Level",
  "salary": 120000
}
```

**Response:**

```json
{
  "success": true,
  "message": "Job posted successfully",
  "job": {
    "_id": "507f1f77bcf86cd799439011",
    "title": "Senior Full Stack Developer",
    "visible": true,
    "date": 1702569600000
  }
}
```

---

## 🗄️ Database Schema

### User Model

```javascript
{
  _id: ObjectId,
  clerkId: String (unique),
  name: String,
  email: String (unique),
  image: String,
  resume: String,  // Cloudinary URL
  createdAt: Date
}
```

### Company Model

```javascript
{
  _id: ObjectId,
  name: String,
  email: String (unique),
  password: String (hashed),
  image: String,  // Cloudinary URL
  createdAt: Date
}
```

### Job Model

```javascript
{
  _id: ObjectId,
  title: String,
  description: String (HTML),
  location: String,
  category: String,
  level: String,
  salary: Number,
  companyId: ObjectId (ref: 'Company'),
  visible: Boolean,
  date: Number (timestamp),
  createdAt: Date
}
```

### JobApplication Model

```javascript
{
  _id: ObjectId,
  companyId: ObjectId (ref: 'Company'),
  userId: String,  // Clerk user ID
  jobId: ObjectId (ref: 'Job'),
  status: String,  // 'Pending', 'Accepted', 'Rejected'
  date: Number (timestamp),
  createdAt: Date
}
```

---

## 📦 Deployment

### Deploying to Vercel

This project is optimized for deployment on **Vercel** with separate deployments for frontend and backend.

#### Prerequisites

- GitHub account
- Vercel account connected to GitHub
- All environment variables ready

---

#### Deploy Backend (Server)

1. **Push code to GitHub**

   ```bash
   git add .
   git commit -m "Initial commit"
   git push origin main
   ```

2. **Import to Vercel**

   - Go to [Vercel Dashboard](https://vercel.com/dashboard)
   - Click **"Add New Project"**
   - Select your GitHub repository
   - Set **Root Directory** to `server`

3. **Configure Environment Variables**

   Add the following in Vercel Dashboard → Settings → Environment Variables:

   - `MONGODB_URI`
   - `CLERK_WEBHOOK_SECRET`
   - `CLOUDINARY_CLOUD_NAME`
   - `CLOUDINARY_API_KEY`
   - `CLOUDINARY_API_SECRET`
   - `SENTRY_DSN`

4. **Deploy**
   - Click **"Deploy"**
   - Note the deployment URL (e.g., `https://your-app.vercel.app`)

---

#### Deploy Frontend (Client)

1. **Import to Vercel**

   - Click **"Add New Project"** again
   - Select the same GitHub repository
   - Set **Root Directory** to `client`

2. **Configure Environment Variables**

   Add the following:

   - `VITE_CLERK_PUBLISHABLE_KEY` → Your Clerk publishable key
   - `VITE_BACKEND_URL` → Your backend Vercel URL from previous step

3. **Build Configuration** (Auto-detected)

   - **Build Command**: `npm run build`
   - **Output Directory**: `dist`
   - **Install Command**: `npm install`

4. **Deploy**
   - Click **"Deploy"**
   - Access your live application!

---

#### Configure Clerk Webhooks

After deployment, configure webhooks to sync user data:

1. Go to [Clerk Dashboard](https://dashboard.clerk.com)
2. Navigate to **Webhooks** → **Add Endpoint**
3. Set endpoint URL: `https://your-backend-url.vercel.app/webhooks`
4. Subscribe to events: `user.created`, `user.updated`
5. Copy the **Signing Secret** and update `CLERK_WEBHOOK_SECRET` in Vercel

---

### Alternative Deployment Options

#### MongoDB Atlas Setup

1. Create a cluster on [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
2. Create a database user
3. Whitelist IP addresses (or allow all: `0.0.0.0/0`)
4. Get connection string and add to environment variables

#### Cloudinary Setup

1. Sign up at [Cloudinary](https://cloudinary.com/)
2. Get credentials from Dashboard → Account Details
3. Configure upload presets if needed

#### Sentry Setup (Optional)

1. Create project at [Sentry](https://sentry.io/)
2. Get DSN from Settings → Client Keys
3. Add to environment variables

---

## 🛠️ Development

### Available Scripts

#### Client Scripts

```bash
npm run dev      # Start Vite dev server
npm run build    # Build for production
npm run preview  # Preview production build
npm run lint     # Run ESLint
```

#### Server Scripts

```bash
npm run server   # Start with nodemon (auto-reload)
npm start        # Start production server
```

---

### Code Structure Guidelines

- **Components**: Reusable UI components in `client/src/components/`
- **Pages**: Route-level components in `client/src/pages/`
- **Controllers**: Business logic in `server/controllers/`
- **Models**: Database schemas in `server/models/`
- **Routes**: API endpoints in `server/routes/`
- **Middleware**: Custom middleware in `server/middleware/`

---

## 🧪 Testing

### Debug Sentry Integration

```bash
curl https://your-backend-url.vercel.app/debug-sentry
```

This endpoint throws a test error to verify Sentry is working.

### Test API Endpoints

```bash
# Get all jobs
curl https://your-backend-url.vercel.app/api/jobs

# Health check
curl https://your-backend-url.vercel.app/
```

---

## 🔒 Security Features

- **Password Hashing**: Bcrypt with salt rounds for company passwords
- **JWT Authentication**: Secure token-based auth for recruiters
- **OAuth Integration**: Clerk handles secure user authentication
- **CORS Configuration**: Controlled cross-origin access
- **Environment Variables**: Sensitive data stored securely
- **Webhook Validation**: Svix verifies Clerk webhook signatures
- **Input Validation**: Server-side validation for all inputs
- **Protected Routes**: Middleware guards sensitive endpoints

---

## 🎨 UI/UX Features

- **Responsive Design**: Mobile-first approach with TailwindCSS
- **Loading States**: Skeleton loaders and spinners
- **Toast Notifications**: Real-time feedback for user actions
- **Rich Text Editing**: Quill editor for job descriptions
- **File Upload**: Drag-and-drop or click-to-upload interface
- **Modal Components**: Overlay forms for authentication
- **Dynamic Routing**: Seamless navigation with React Router
- **Context API**: Global state management for user/company data

---

## 📊 Features Breakdown

### Job Management System

- ✅ Create, Read, Update, Delete (CRUD) operations
- ✅ Rich text job descriptions with HTML formatting
- ✅ Job categories: Programming, Design, Marketing, etc.
- ✅ Experience levels: Fresher, Mid Level, Senior Level
- ✅ Salary display with formatted numbers (e.g., 50K, 100K)
- ✅ Location-based filtering
- ✅ Visibility toggle (show/hide jobs)
- ✅ Timestamp-based job posting dates

### Application Management System

- ✅ One-click job applications
- ✅ Resume upload and management
- ✅ Application status tracking (Pending, Accepted, Rejected)
- ✅ Company-side application reviews
- ✅ Bulk application viewing
- ✅ Filter applications by job
- ✅ Real-time status updates

### User Role System

**Job Seekers:**

- Browse and search jobs
- Apply with uploaded resume
- Track application status
- Update profile and resume

**Recruiters/Companies:**

- Post and manage job listings
- Review applications
- Update application status
- Manage company profile
- Control job visibility

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

### How to Contribute

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Commit your changes**
   ```bash
   git commit -m 'Add some amazing feature'
   ```
4. **Push to the branch**
   ```bash
   git push origin feature/amazing-feature
   ```
5. **Open a Pull Request**

### Code Style

- Follow existing code formatting
- Use ESLint for JavaScript linting
- Write meaningful commit messages
- Add comments for complex logic
- Test before submitting PR

---

## 📝 License

This project is licensed under the **ISC License**.

---

## 👨‍💻 Author

**Dheerendra**

- GitHub: [@dheerendra45](https://github.com/dheerendra45)
- Project Link: [Job Portal App](https://github.com/dheerendra45/jobportal)

---

## 🙏 Acknowledgments

- **GreatStack** - For guidance and best practices
- **Clerk** - For seamless authentication
- **Vercel** - For deployment platform
- **MongoDB** - For database infrastructure
- **Cloudinary** - For media management
- **Sentry** - For error monitoring
- **Open Source Community** - For amazing tools and libraries

---

## 📞 Support

If you like this project, please ⭐ star this repository!

For questions or support, please open an issue on GitHub.

---

<div align="center">

**Built with ❤️ using the MERN Stack**

[⬆ Back to Top](#-job-portal-app)

</div>
