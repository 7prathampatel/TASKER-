# Tasker - Project and Task Management System

[Live Project Link](https://tasker07.vercel.app/)

---

## 📌 Introduction

**Tasker** is a lightweight yet powerful **Project and Task Management System** that allows users to organize projects, manage tasks, handle issues, and collaborate inside organizations seamlessly — without any admin panels or complex roles.  
Designed for modern teams and individuals, Tasker ensures easy onboarding, clear task assignment, real-time tracking, and email notifications — all in a minimal and efficient user experience.

Built with a **scalable, secure, and modern tech stack**, including React.js, Prisma ORM, NeonDB, and Clerk Authentication, Tasker helps teams stay productive and focused.

---

## ✨ Key Features

- 🔒 **Authentication** via **Clerk** (Login/Signup/Email Verification)
- 🏢 **Organization Management** (Create, Join, Manage)
- 📁 **Project Management** (Create, Update, Delete Projects)
- 📝 **Task Management** (Create, Assign, Track Tasks)
- 🛠️ **Issue Tracking** (Create and Resolve Task Issues)
- 🧩 **Split Management** (Subtasks under Tasks)
- 📩 **Email Notifications** (Invitations, Notifications via Clerk)
- 🗄️ **Data Storage** in **NeonDB** via Prisma ORM
- 🎨 **Modern and Responsive UI** with Tailwind CSS and Shadcn UI
- ⚡ **High Performance** - Built with best coding practices
- 🚀 **Deployed Live** at: [https://tasker07.vercel.app/](https://tasker07.vercel.app/)

---

## 🏛 System Overview

Tasker removes unnecessary complexity from project management. There’s no admin dashboard, no role-based access controls — just seamless collaboration inside organizations.  
Users sign up via Clerk, create or join organizations, and start managing projects, tasks, issues, and splits easily.

- **Authentication**: Handled entirely by **Clerk**
- **Database**: Managed by **NeonDB** (PostgreSQL) via **Prisma ORM**
- **Email Notifications**: Handled securely via Clerk

**Main Modules**:
- Organization
- Project
- Task
- Issue
- Split (Subtasks)
- Notification (Email-Based)

---

## ⚙️ Tech Stack

| Layer          | Technology                         |
|----------------|-------------------------------------|
| Frontend       | React.js + Tailwind CSS + Shadcn UI |
| Backend ORM    | Prisma ORM                          |
| Database       | NeonDB (Serverless PostgreSQL)      |
| Authentication | Clerk.dev                           |
| Hosting        | Vercel                              |
| Diagram Tools  | PlantUML (DFD, Sequence Diagrams)   |

---

## 🔐 Authentication Flow

- User signs up/signs in via **Clerk**
- Clerk handles:
  - Email verification
  - Sessions (JWT based)
  - Password management
  - Invitations via email
- After successful login:
  - User can create or join an organization
  - All future actions happen inside their organization context

**Important**:  
There is **no admin role**. Every authenticated user has equal access inside an organization.

---

## 📚 Database Design

Tables Used:

| Table Name    | Purpose                               |
|---------------|---------------------------------------|
| User          | Stores Clerk user ID and details      |
| Organization  | Stores organization data             |
| Membership    | Links Users to Organizations          |
| Project       | Stores projects under organizations  |
| Task          | Manages tasks under projects          |
| Issue         | Tracks issues related to tasks        |
| Split         | Tracks subtasks of tasks              |

- All relationships are maintained using Prisma's relational mappings.
- All IDs are UUIDs for security and scalability.

---

## 🛠️ Installation and Setup

Follow the steps below to run Tasker locally:

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/tasker.git
cd tasker
2. Install Dependencies
bash
Copy
Edit
npm install
3. Configure Environment Variables
Create a .env file in the root with:

env
Copy
Edit
NEXT_PUBLIC_CLERK_FRONTEND_API=your-clerk-frontend-api
CLERK_SECRET_KEY=your-clerk-secret-key
DATABASE_URL=your-neon-db-url
NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in
NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up
NEXT_PUBLIC_CLERK_AFTER_SIGN_IN_URL=/
NEXT_PUBLIC_CLERK_AFTER_SIGN_UP_URL=/
4. Run Prisma
bash
Copy
Edit
npx prisma generate
npx prisma migrate dev --name init
5. Start the Server
bash
Copy
Edit
npm run dev
Project will run at: http://localhost:3000

🧩 Folder Structure
bash
Copy
Edit
/components    → Reusable React components
/pages         → Next.js Pages and Routing
/lib           → Prisma client and Clerk client
/prisma        → Prisma schema and migrations
/public        → Static assets (images, icons)
/styles        → Tailwind CSS files
/utils         → Helper functions
README.md      → Documentation
🗺 Diagrams
Data Flow Diagram (DFD)
Level 0:

User → Tasker System (Authentication, Task, Project Management)

Level 1:

User requests Login (→ Clerk)

User requests Create Organization (→ Database)

User adds Project/Task/Issue (→ Database)

Clerk handles Notifications (→ User via Email)

✨ Major Modules and Processes
1. User Authentication
Sign Up

Email Verification

Session Management (JWT)

2. Organization Management
Create Organization

Invite Members

Manage Memberships

3. Project Management
Create Project

Update Project

Delete Project

4. Task Management
Create Tasks under Projects

Update Tasks

Delete Tasks

Assign Members

5. Issue Management
Create and track issues related to tasks

Resolve issues

6. Split (Subtasks) Management
Break larger tasks into splits

7. Notifications
Email notification for invites and alerts via Clerk

🚀 Future Enhancements
Real-time collaboration (WebSocket integration)

Comment threads on tasks and issues

Gantt Charts for project tracking

Export project reports in PDF/Excel

Public organization links

Task reminders

Role-based permission system (optional, not admin-specific)

📖 References
Clerk Documentation - https://clerk.dev/docs

Prisma ORM - https://www.prisma.io/docs

Neon Database - https://neon.tech/docs

React Documentation - https://react.dev/

Tailwind CSS Documentation - https://tailwindcss.com/docs

Vercel Hosting - https://vercel.com/docs

🎓 About UVPCE College
Institute: U. V. Patel College of Engineering (UVPCE)

Location: Ganpat University, Mehsana, Gujarat

Website: https://www.uvpce.ac.in

🏢 About Organization
Clerk
Clerk provides authentication and user management APIs for developers building modern web and mobile apps.

NeonDB
NeonDB is a serverless Postgres database designed for cloud-native applications.

Vercel
Vercel is a hosting and serverless deployment platform built for Next.js, React, and other frameworks.

📃 License
This project is licensed under the MIT License.
You are free to use, modify, and distribute the software.

🎯 Conclusion
Tasker represents a new era of lightweight, easy-to-use, and highly collaborative project management tools.
By removing complex admin controls and focusing on collaboration, real-time task management, and seamless notifications, Tasker helps modern teams stay agile, productive, and efficient.

With cutting-edge tools like Clerk authentication, NeonDB's serverless database, Prisma ORM's type-safety, and the responsiveness of React.js and TailwindCSS — Tasker is built for the future of team collaboration.

Visit the live project here:
👉 Tasker - Project and Task Management System


