# Blueprint: Next.js + PostgreSQL example

> **Blueprint branch · one example, not a requirement.**
> This branch contains a small Next.js + PostgreSQL application from the 2025 edition of the Article26 Hackathon.
> It shows one possible way to set up persistence, API routes, Swagger and Docker Compose.
> The 2026 challenge and the build guide are on the [`main` branch](../../tree/main). Choose your own stack.


## 📋 Table of Contents

- [🛠️ Installation Requirements](#️-installation-requirements)
- [🚀 Quick Start](#-quick-start)
- [📁 Repository Structure](#-repository-structure)

## 🛠️ Installation Requirements

To participate in this hackathon, you'll need to install the following tools:

### 1. Git
Git is required to clone the repository and manage version control.

**Download and Install:**
- **Windows**: Download from [git-scm.com](https://git-scm.com/download/win)
- **Mac**: Install via Homebrew `brew install git` or download from [git-scm.com](https://git-scm.com/download/mac)
- **Linux**: Install via package manager (e.g., `sudo apt install git` on Ubuntu)

**Verify Installation:**
```bash
git --version
```

### 2. Docker Desktop
Docker is used to run the PostgreSQL database and Adminer (database management tool).

**Download and Install:**
- **Windows/Mac**: Download from [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- **Linux**: Follow the [Docker Engine installation guide](https://docs.docker.com/engine/install/)

**Verify Installation:**
```bash
docker --version
docker-compose --version
```

### 3. Node.js
The application is built with Next.js, requiring Node.js version 18 or higher.

**Download and Install:**
- Download from [nodejs.org](https://nodejs.org/) (LTS version recommended)
- Or use a version manager like [nvm](https://github.com/nvm-sh/nvm)

**Verify Installation:**
```bash
node --version
npm --version
```

### 4. Visual Studio Code
Recommended IDE with excellent TypeScript and React support.

**Download and Install:**
- Download from [code.visualstudio.com](https://code.visualstudio.com/)

**Recommended Extensions:**
- ES7+ React/Redux/React-Native snippets
- TypeScript Importer
- Prettier - Code formatter
- ESLint
- Tailwind CSS IntelliSense

## 🚀 Quick Start

1. **Clone the repository**
   ```bash
   git clone https://github.com/DanielStuewe/article26-hackathon-2026.git
   cd article26-hackathon-2026
git switch blueprint
   ```

2. **Start the database**
   ```bash
   docker-compose up -d
   ```

3. **Install dependencies and setup the application**
   ```bash
   npm install
   npm run seed
   ```

4. **Start the development server**
   ```bash
   npm run dev
   ```

5. **Access the application**
   - Application: http://localhost:3000
   - Database Admin: http://localhost:8080

6. **Verify the setup is working**
   
   When everything is set up correctly, you should see the example application running:

   ![Example Application Screenshot](example-app-screenshot.png)
   
   *The application should display the time booking interface with user management functionality.*

## 📁 Repository Structure

This repository is organized as follows:

```
article26-hackathon/
├── .env.local                     # Environment variables for local development
├── .gitignore                     # Git ignore file
├── compose.yaml                   # Docker Compose configuration for database
├── LICENSE                        # MIT License
├── README.md                      # This file
├── NEXTJS_README.md              # Next.js specific documentation
├── example-app-screenshot.png    # Screenshot of the working application
├── package.json                  # Node.js dependencies and scripts
├── next.config.ts                # Next.js configuration
├── tsconfig.json                 # TypeScript configuration
├── postcss.config.mjs            # PostCSS configuration
├── db.ts                         # Database connection utilities
├── seed-database.js              # Database seeding script
├── DATABASE_SETUP.md             # Database setup instructions
├── app/                          # Next.js App Router directory
│   ├── layout.tsx                # Root layout component
│   ├── page.tsx                  # Home page
│   ├── globals.css               # Global CSS styles
│   ├── favicon.ico               # Application favicon
│   ├── add-user/                 # User management page
│   │   └── page.tsx              # Add user page component
│   ├── api/                      # API routes
│   │   └── users/                # User API endpoints
│   │       └── route.ts          # User CRUD operations
│   └── components/               # Reusable React components
│       └── Header.tsx            # Header component
└── public/                       # Static assets
    ├── *.svg                     # Various SVG icons
    └── image.png                 # Sample image
```

### Key Components:

**🐳 Docker Setup (`compose.yaml`)**
- PostgreSQL database (port 5432)
- Adminer database management tool (port 8080)
- Pre-configured with sample credentials

**⚛️ Next.js Application (Root Directory)**
- **Framework**: Next.js 15 with App Router
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **UI Components**: PrimeReact
- **Database**: PostgreSQL with pg driver

**📊 Database**
- PostgreSQL with Docker Compose
- Seeding script for sample data
- Adminer for database management
