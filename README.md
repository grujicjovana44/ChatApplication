# Chat Application

## 🚀 About the Project

A full-stack chat application that enables users to communicate in real time, share files, create group conversations, and report inappropriate content.

### Key Features
- Real-time messaging using Socket.IO
- Private and group conversations
- Image and document sharing
- GIF search and sharing
- Online/offline status tracking
- Message editing and deletion
- Content reporting and moderation

## 🛠 Tech Stack

### Backend
- **Node.js** and **Express.js** — Server framework
- **TypeScript** — Type safety
- **TypeORM** — Object-relational mapping for SQLite/PostgreSQL
- **Socket.IO** — Real-time communication
- **JWT** — Authentication
- **Nodemailer** — Email services

### Frontend
- **Next.js 14** — React framework
- **TypeScript** — Type safety
- **Tailwind CSS** — Styling
- **Socket.IO Client** — Real-time communication
- **React Hook Form** and **Zod** — Form handling and validation
- **Axios** — HTTP client

### DevOps and Documentation
- **Docker** and **Docker Compose** — Containerization
- **GitHub Actions** — CI/CD automation
- **Swagger** — API documentation

## ✨ Features

### 👤 User Management
- User registration and login
- Password reset via email
- User profiles
- Private and group chat creation
- Sending and receiving messages
- Online/offline status

### 💬 Messaging
- Real-time message delivery
- Message editing and deletion
- Image and document sharing
- GIF search and sharing via the Giphy API
- Emoji picker integration

### 👥 Group Chats
- Group creation
- Adding and removing members
- Admin and moderator roles

### 🛡 Security
- JWT-based authentication
- HttpOnly cookies and SameSite cookie attributes
- Input validation and sanitization
- Protection against SQL injection through parameterized queries
- Configurable CORS policies
- Rate limiting
- Resource ownership checks to mitigate IDOR vulnerabilities
- Content Security Policy (CSP) headers

## 🌐 External APIs and Services

| Service | Purpose |
|---|---|
| Cloudinary | File uploads and media hosting |
| Giphy API | GIF search and sharing |
| Gmail SMTP | Email delivery |

## 🔒 Security Measures

The application incorporates several security mechanisms designed to reduce common web application vulnerabilities.

### 1. CSRF (Cross-Site Request Forgery)
- HttpOnly cookies to prevent JavaScript access to authentication cookies
- SameSite cookie attributes to help mitigate cross-site request forgery

### 2. XSS (Cross-Site Scripting)
- Input validation using Zod schemas
- Sanitization of user-provided input
- Content Security Policy headers

### 3. SQL Injection
- Parameterized queries through TypeORM
- ORM-managed query construction to reduce SQL injection risks

### 4. CORS (Cross-Origin Resource Sharing)
- Allowlist-based origin configuration
- Credentials enabled only for authorized frontend origins

### 5. IDOR (Insecure Direct Object Reference)
- Authentication and authorization checks on protected routes
- Resource ownership validation

## 🚀 Getting Started

### Prerequisites
- Node.js 18 or later
- Docker and Docker Compose
- Git

### 1. Clone the Repository

```bash
git clone https://github.com/elab-development/internet-tehnologije-2025-chataplikacija_2022_0376.git
cd internet-tehnologije-2025-chataplikacija_2022_0376
```

### 2. Configure Environment Variables

Create a `.env` file in the backend directory.

**Backend (`backend/.env`):**

```env
# Server
PORT=5000
NODE_ENV=development

# Database
DB_HOST=localhost
DB_PORT=5432
DB_USER=postgres
DB_PASSWORD=postgres
DB_NAME=chat_db

# JWT
JWT_SECRET=your-secret-key-here
JWT_EXPIRES_IN=7d

# CORS
FRONTEND_URL=http://localhost:3000

# Cloudinary
CLOUDINARY_CLOUD_NAME=your-cloud-name
CLOUDINARY_API_KEY=your-api-key
CLOUDINARY_API_SECRET=your-api-secret

# SMTP (Gmail)
SMTP_EMAIL=your-email@gmail.com
SMTP_PASSWORD=your-app-password
```

Create a `.env.local` file in the frontend directory.

**Frontend (`frontend/.env.local`):**

```env
NEXT_PUBLIC_API_URL=http://localhost:5000/api
NEXT_PUBLIC_WS_URL=http://localhost:5000
NEXT_PUBLIC_GIPHY_API_KEY=your-giphy-key
```

Replace the placeholder values with your own credentials. Never commit real secrets or API keys to version control.

### 3. Run with Docker Compose

From the project root, run:

```bash
docker-compose up --build
```

### 4. Run Locally Without Docker

**Backend:**

```bash
cd backend
npm install
npm run dev
```

**Frontend:**

Open a separate terminal and run:

```bash
cd frontend
npm install
npm run dev
```

### 5. Access the Application

Once the services are running, use the following endpoints, provided they match your local configuration:

- **Frontend:** http://localhost:3000
- **Backend:** http://localhost:5000
- **API Documentation:** http://localhost:5000/api-docs
- **Health Check:** http://localhost:5000/health

## 📚 API Documentation

The API documentation is available through Swagger at:

http://localhost:5000/api-docs

Make sure the backend is running before accessing the documentation.

## 🧪 Testing

### Unit Tests

```bash
cd backend
npm run test
```

### Integration Tests

```bash
cd backend
npm run test:integration
```

### End-to-End Tests with Cypress

```bash
cd frontend
npm run cypress:open
```

Run the commands supported by the scripts defined in the relevant `package.json` files.

## 🔄 Development Workflow

### 1. Create a Feature Branch

```bash
git checkout develop
git pull origin develop
git checkout -b feature/new-feature
```

### 2. Commit Your Changes

```bash
git add .
git commit -m "feat: add new feature"
```

### 3. Push and Open a Pull Request

```bash
git push origin feature/new-feature
```

Open a Pull Request to merge your changes into the appropriate target branch.

## 📊 CI/CD Pipeline

The GitHub Actions workflow (`.github/workflows/ci-cd.yml`) is intended to automate the delivery pipeline, including:

1. Running automated tests
2. Building Docker images
3. Publishing images to Docker Hub
4. Deploying the application to a cloud environment

The actual pipeline steps depend on the workflow configuration and the deployment credentials available in the repository.
