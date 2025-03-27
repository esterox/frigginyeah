# Frigginyeah rebuild

This project is a **Next.js 10.0.3** application. Follow the instructions below to configure, build, and run the project.

---

## Prerequisites

Before you begin, ensure you have the following installed:
- **Node** v14.15.5

---

## Setup

### 1. Clone the Repository
Clone this repository to your local machine:
```bash
git clone <repository-url>
cd <repository-directory>
```

### 2. Configure Environment Variables
Copy the example environment file `.env.example` to `.env` and provide the required values:
```bash
cp .env.example .env
```
Update the `.env` file with values specific to your environment.

### 3. Install Dependencies and Seed the Database
Run the following commands to install required packages and seed the database:
```bash
npm install
npm run seed
```

### 4. Start the Development Server
To run the application in development mode, execute:
```bash
npm run dev
```

---

## Deployment

### Prerequisite
Ensure you have the `fy-dev.pem` file on your local machine and set the correct permissions:
```bash
chmod 400 fy-dev.pem
```

### 1. Connect to the Server
```bash
ssh -i "fy-dev.pem" ubuntu@54.185.11.204 -p 22
```

### 2. Navigate to the Project Directory
```bash
cd frigginyeah_rebuild
```

### 3. Pull the Latest Changes from GitLab
```bash
git pull origin dev
```

### 4. Install Dependencies
```bash
npm i
```

### 5. Build the Application
```bash
npm run build
```

### 6. Restart the Application with PM2

Delete the existing PM2 process:
```bash
pm2 delete 0
```

Start the application:
```bash
pm2 start ecosystem.config.js --env production
```

### 7. Exit the Server
```bash
exit
```

