# 🛠️ AAM – Project Setup Guide

This guide will help you run everything **locally** on your computer

---

## 📁 Project Structure

```
Tech-Collab/
│
├── frontend/         # React JS app
├── backend/          # Laravel API
└── AI-features/      # Python FastAPI for AI features
```

---

## 🚀 Prerequisites – What You Need to Install

### For macOS Users

Install each of the following tools (you can copy-paste commands into your terminal):

1. **Install Homebrew (if not already installed):**
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. **Install Node.js & npm:**
   ```bash
   brew install node
   ```

3. **Install Composer (PHP package manager):**
   ```bash
   brew install composer
   ```

4. **Install PHP:**
   ```bash
   brew install php
   ```

5. **Install MySQL (choose port 8889 when prompted by Laravel):**
   ```bash
   brew install mysql
   brew services start mysql
   ```

6. **Install Python 3 and pip:**
   ```bash
   brew install python
   ```

---

### For Windows Users

1. **Install Node.js:**  
   [Download Node.js LTS version](https://nodejs.org)

2. **Install Composer:**  
   [Download Composer Installer](https://getcomposer.org/download/)

3. **Install XAMPP (includes PHP & MySQL):**  
   [Download XAMPP](https://www.apachefriends.org/index.html)  
   → Once installed, open XAMPP Control Panel and start **MySQL** (no need to start Apache).

4. **Install Python 3 (includes pip):**  
   [Download Python](https://www.python.org/downloads/)  
   → Be sure to check the box **“Add Python to PATH”** during installation.

---

## 🔧 Setting Up the Project

Follow these steps in order for a successful setup:

---

### 1️⃣ Clone the Project

```bash
git clone https://github.com/jaafarhawli/Tech-Collab.git
cd Tech-Collab
```

---

### 2️⃣ Setup the Backend (Laravel)

```bash
cd backend
composer install
copy .env.example .env
```

Update the `.env` file as needed:

#### Create the Database

- macOS: 
  ```bash
  mysql -u root -p
  CREATE DATABASE tech_collab;
  ```

- Windows:  
  Use **phpMyAdmin** (from XAMPP) → Create a new database named `tech_collab`

#### Generate Laravel Key and Migrate DB

```bash
php artisan key:generate
php artisan migrate
php artisan db:seed
php artisan serve
```

Your Laravel API will now be running on:  
**http://localhost:8000**

---

### 3️⃣ Setup the Frontend (React)

```bash
cd ../frontend
npm install
copy .env.example .env
npm run dev
```

React app should now be available at:  
**http://localhost:5173**

---

### 4️⃣ Setup the AI API (FastAPI)

```bash
pip install -r AI-features/requirements.txt
python AI-features/main.py
```

This will run the AI server at:  
**http://localhost:8001**

---

## ✅ Final Check – Running Apps

| App        | URL                         | Command                        |
|------------|-----------------------------|--------------------------------|
| Laravel    | http://localhost:8000       | `php artisan serve`           |
| React JS   | http://localhost:5173       | `npm run dev`                 |
| FastAPI    | http://localhost:8001       | `python AI-features/main.py`  |

---

## 🙌 You're Done!

You now have the full stack running locally on your machine.  
If you need any help, feel free to open an issue or contact the team.

Happy coding! 💻✨
