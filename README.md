# 🚀 Real-Time Chat Application (Socket.io, MERN)

This project is a **full-stack real-time chat application** built using:

* **React + Vite** (Frontend)
* **Node.js + Express + MongoDB** (Backend)
* **Socket.io** for real-time communication
* **Render** for backend deployment
* **Vercel** for frontend deployment
* **GitHub Actions** for automated CI/CD

---

## 📌 Live URLs

| Service               | URL                                                                                        |
| --------------------- | ------------------------------------------------------------------------------------------ |
| **Frontend (Vercel)** | [https://socketio-chat-app-kappa.vercel.app/](https://socketio-chat-app-kappa.vercel.app/) |
| **Backend (Render)**  | [https://chart-xxyc.onrender.com](https://chart-xxyc.onrender.com)                         |

---

## 📁 Project Structure

```
socketio-chat/
├── client/                 # React front-end
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   ├── context/
│   │   ├── hooks/
│   │   ├── pages/
│   │   ├── socket/
│   │   └── App.jsx
│   └── package.json
│
├── server/                 # Node.js back-end
│   ├── config/
│   ├── controllers/
│   ├── models/
│   ├── socket/
│   ├── utils/
│   ├── server.js
│   └── package.json
│
└── README.md
```

---

# ✅ 1. Deployment Tasks Completed

### **Frontend Deployment (Vercel)**

* Built with **Vite + React**
* Connected to GitHub for automatic deployments
* Environment variables added via Vercel Dashboard
* Production URL generated automatically

### **Backend Deployment (Render)**

* Render **Web Service**
* Auto-deploy from GitHub repository
* `.env` variables configured in Render Dashboard
* MongoDB connected using **MongoDB Atlas URI**
* Live server URL configured for CORS and Socket.io

---

# ⚙️ 2. CI/CD Pipeline With GitHub Actions

A **full CI/CD pipeline** was created using GitHub Actions to:

✔️ Install dependencies
✔️ Run build steps
✔️ Test the code (optional)
✔️ Deploy frontend to **Vercel**
✔️ Deploy backend to **Render**

### **.github/workflows/deploy.yml**

```yaml
name: CI/CD Pipeline

on:
  push:
    branches: 
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Setup Node
        uses: actions/setup-node@v3
        with:
          node-version: 18

      - name: Install dependencies
        run: npm install

      - name: Build client
        run: |
          cd client
          npm install
          npm run build

      - name: Deploy Frontend to Vercel
        run: |
          npm i -g vercel
          vercel deploy --prod --token=${{ secrets.VERCEL_TOKEN }}

      - name: Deploy Backend to Render
        run: |
          curl -X POST ${{ secrets.RENDER_DEPLOY_HOOK_URL }}
```

---

# 🚀 3. Deployment to Production

### **Frontend (Vercel)**

✔ Linked to GitHub
✔ Auto builds on push to `main`
✔ Production preview for each commit
✔ Global CDN

### **Backend (Render)**

✔ Auto deploys from `main`
✔ Node version & start command configured
✔ Environment variables secure
✔ Deployed as Web Service
✔ Health checks enabled

---

# 📝 4. Documentation of Deployment Process

### **Step 1 – Push Code to GitHub**

All code from backend+frontend was pushed to a unified repo.

### **Step 2 – Deploy Backend on Render**

* Created **Web Service**
* Linked to GitHub repo
* Set build command: `npm install`
* Set start command: `node server.js`
* Added environment variables (`PORT`, `MONGO_URI`, etc.)
* Enabled *Auto Deploy*

### **Step 3 – Deploy Frontend on Vercel**

* Imported GitHub repo into Vercel
* Build command: `npm run build`
* Output directory: `dist`
* Added environment variables (API URL)
* Deployed with CI/CD integration

### **Step 4 – Enabled CI/CD with GitHub Actions**

* Added workflow file under `.github/workflows/`
* Connected Vercel token → GitHub Secrets
* Added Render deploy hook → GitHub Secrets

### **Step 5 – Verified Production**

* Confirmed backend is online
* Confirmed frontend points to correct backend URL
* Confirmed sockets work (real-time chat, presence, notifications)

---

```md
### CI/CD Pipeline Running
![Pipeline](cicd.png)
```

---

# 🌍 6. Final Deployed URLs

### **Frontend App (Vercel)**

🔗 [https://socketio-chat-app-kappa.vercel.app/](https://socketio-chat-app-kappa.vercel.app/)

### **Backend API (Render)**

🔗 [https://chart-xxyc.onrender.com](https://chart-xxyc.onrender.com)

---

# 🛠 Technologies Used

| Layer         | Tech                                 |
| ------------- | ------------------------------------ |
| Frontend      | React, Vite, Context API, Socket.io  |
| Backend       | Node.js, Express, MongoDB, Socket.io |
| DevOps        | Render, Vercel, GitHub Actions       |
| Communication | WebSockets                           |

---

# 📦 Installation (Local Development)

```
git clone <your_repo_url>
cd socketio-chat

# install client
cd client
npm install
npm run dev

# install server
cd ../server
npm install
npm run dev
```

---

# 🤝 Contributing

Pull requests are welcome!
Please open an issue first for discussion.

---


