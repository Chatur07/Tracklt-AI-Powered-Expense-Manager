# 📊 Tracklt – AI-Powered Expense Manager
A full-stack personal finance management application combining a **C++ backend** with a **Node.js/Express web interface**, enriched by a **Python-based anomaly detection model**. Track expenses, manage budgets, receive personalized recommendations, and get alerts for unusual transactions.

---

## 📷 Screenshots

<div align="center">
  <img src="https://github.com/Chatur07/Tracklt-Intelligent-Personal-Finance-Management/blob/main/project_ss/ss1.png" width="600"/>
  <img src="https://github.com/Chatur07/Tracklt-Intelligent-Personal-Finance-Management/blob/main/project_ss/ss2.png" width="600"/>
  <img src="https://github.com/Chatur07/Tracklt-Intelligent-Personal-Finance-Management/blob/main/project_ss/ss3.png" width="600"/>
  <img src="https://github.com/Chatur07/Tracklt-Intelligent-Personal-Finance-Management/blob/main/project_ss/ss4.png" width="600"/>
  <img src="https://github.com/Chatur07/Tracklt-Intelligent-Personal-Finance-Management/blob/main/project_ss/ss5.png" width="600"/>
  <img src="https://github.com/Chatur07/Tracklt-Intelligent-Personal-Finance-Management/blob/main/project_ss/ss6.png" width="600"/>
</div>

---

## 🧭 Navigation

* [Features](#features)
* [Tech Stack](#tech-stack)
* [Installation](#installation)
* [API Endpoints](#api-endpoints)
* [Project Structure](#project-structure)
* [Usage](#usage)
* [Prerequisites](#prerequisites)
* [Security](#security)
* [Contributing](#contributing)
* [Support](#support)

---

## 🚀 Features

### ✅ Core Features

* User registration & login with JWT
* Add, view, and manage transactions
* Set and track budgets per category
* View visualized spending analytics
* Personalized recommendations using a priority queue
* **Anomaly Detection**: Detects suspicious transactions using Isolation Forest (94.63% accuracy)

### 📁 Categories

* Food
* Shopping
* Entertainment
* Personal
* Health
* Travel
* Rent
* Income
* Miscellaneous

---

## 🧱 Tech Stack

### ⚙️ Backend

* C++ (core logic, file-based data handling)

  * Doubly linked lists
  * Priority queue
* Node.js + Express.js (API server)
* JWT (for authentication)
* **Python + Flask** (Anomaly detection)

  * Isolation Forest ML model

### 🎨 Frontend

* HTML / CSS / JavaScript
* REST API integration

---

## 🛠️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/Luv-valecha/Finance_Tracker.git
cd Finance_Tracker
```

### 2. Install Node.js dependencies

```bash
npm install
```

### 3. Compile C++ Backend

```bash
cd backend
g++ -o finance_tracker main.cpp Login_system.cpp Transactions.cpp post_data.cpp get_data.cpp BudgetNRecommender.cpp Statistics.cpp
```

### 4. Set up Python Anomaly Detection server

```bash
cd backend/Anomaly_Detection_Model
pip install -r requirements.txt
python anomaly_detector.py
```

### 5. Create environment file

```bash
# .env
PORT=3000
```

### 6. Start Node.js Server

```bash
cd frontend
node server.js
```

---

## 📡 API Endpoints

### 🔐 Authentication

```
POST /api/register           # Register new user
POST /api/login              # Login user
GET  /api/logout             # Logout user
```

### 💸 Transactions

```
POST /api/add-transaction       # Add new transaction
GET  /api/transactions          # Get all transactions
GET  /api/cattransactions       # Filter by category
GET  /api/daterangetransactions# Filter by date range
POST /api/detect-anomaly        # Run anomaly detection
```

### 📊 Budget & Analytics

```
POST /api/setbudget             # Set category budgets
GET  /api/categorywisespend     # Get breakdown by category
GET  /api/getrecommendation     # View suggestions
```

---

## 🗂️ Project Structure

```
├── backend/
│   ├── main.cpp
│   ├── Login_system.*
│   ├── Transactions.*
│   ├── Transhist.h
│   ├── post_data.cpp
│   ├── get_data.cpp
│   ├── BudgetNRecommender.cpp
│   ├── Statistics.cpp
│   └── Anomaly_Detection_Model/
│       ├── anomaly_detector.py
│       ├── requirements.txt
│       ├── encoder.pkl
│       ├── scaler.pkl
│       └── anomaly_detection_model.pkl
├── frontend/
│   ├── public/
│   │   ├── index.html
│   │   ├── register.html 
│   │   ├── dashboard.html
│   │   ├── css/
│   │   │   ├── images/
│   │   │   └── style.css
│   │   └── js/
│   │       ├── app.js
│   │       └── utils.js
│   ├── routes/
│   │   └── api.js
│   └── server.js
├── package.json
└── README.md
```

---

## 📘 Usage

1. **Register** a new account at `/register`
2. **Login** via `/login` (JWT token will be returned)
3. **Add Transactions**

   * Provide date, amount, category, description
4. **View Transactions**

   * Filter by category, type, or date range
5. **Manage Budgets**

   * Set category-wise budgets
   * Receive insights & warnings
6. **Anomaly Detection**

   * Flask server checks for suspicious activity
   * User confirms or rejects detected anomalies
   * Requires Python server to be running

---

## 📌 Prerequisites

* Node.js & npm
* C++ compiler (e.g., g++)
* Python 3.x
* Python dependencies (`pip install -r requirements.txt`)

---

## 🔐 Security

* Passwords hashed & secured
* JWT-based authentication
* Input validation
* Safe file operations

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature-name`)
3. Commit changes (`git commit -m 'Add feature'`)
4. Push (`git push origin feature-name`)
5. Open a pull request

