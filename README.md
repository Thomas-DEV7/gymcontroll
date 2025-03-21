
# GymControll

GymControll is a web application that helps users manage their workout routines and track their progress over time. With a focus on simplicity and a user-friendly interface, GymControll allows users to create personalized training routines, add exercises, and log each execution with weight and repetitions. It also provides progress analysis with dynamic charts.

---

## 🚀 Features

- User Registration and Authentication (Sign up / Login / Logout)
- Create and Manage Training Routines
- Add Exercises to Each Routine
- Log Executions (Weight & Repetitions)
- View Exercise History and Performance
- Analyze Progress with Charts (Chart.js)
- Toast Notifications for User Feedback
- Dark Theme with Responsive Design (Mobile First)
- Simple, Intuitive Interface
- Developed with Pure PHP (No Frameworks)

---

## 🛠️ Technologies Used

- PHP (Pure)
- MySQL (Database)
- Bootstrap 5 (Responsive UI)
- Chart.js (Progress Visualization)
- Vanilla JavaScript (Frontend Interactions)
- XAMPP (Local Development Environment)

---

## 📂 Project Structure

```
gymcontroll/
├── assets/
│   ├── css/
│   │   └── style.css
│   └── js/
│       └── scripts.js
├── config/
│   └── database.php
├── controllers/
│   ├── AuthController.php
│   ├── TrainingController.php
│   ├── ExerciseController.php
│   └── ExecutionController.php
├── includes/
│   ├── header.php
│   ├── footer.php
│   └── navbar.php
├── models/
│   ├── User.php
│   ├── Exercise.php
├── public/
│   ├── index.php
│   ├── login.php
│   ├── cadastro.php
│   ├── dashboard.php
│   ├── training_detail.php
│   └── exercise_detail.php
├── toasts/
│   └── toast.php
└── README.md
```

---

## ⚙️ Installation Guide

### 1. Clone the Repository
```
git clone https://github.com/yourusername/gymcontroll.git
```

### 2. Move into the Project Folder
```
cd gymcontroll
```

### 3. Import the Database
- Create a database named `gymcontroll` in phpMyAdmin.
- Run the following SQL scripts to create the necessary tables:

```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE trainings (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT NOT NULL,
    name VARCHAR(100) NOT NULL,
    description TEXT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE
);

CREATE TABLE exercises (
    id INT AUTO_INCREMENT PRIMARY KEY,
    training_id INT NOT NULL,
    name VARCHAR(100) NOT NULL,
    description TEXT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (training_id) REFERENCES trainings(id) ON DELETE CASCADE
);

CREATE TABLE executions (
    id INT AUTO_INCREMENT PRIMARY KEY,
    exercise_id INT NOT NULL,
    weight DECIMAL(5,2) NOT NULL,
    repetitions INT NOT NULL,
    execution_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (exercise_id) REFERENCES exercises(id) ON DELETE CASCADE
);
```

### 4. Configure the Database Connection
Edit the `config/database.php` file if necessary:

```php
$host = 'localhost';
$dbname = 'gymcontroll';
$username = 'root';
$password = ''; // Default password in XAMPP
```

### 5. Start the XAMPP Services
- Start Apache and MySQL through XAMPP Control Panel.
- Access the application at:
```
http://localhost/gymcontroll/public/login.php
```
# Structure

<pre>
    gymcontroll/
    ├── assets/ 
    │ ├── css/ 
    │ └── style.css 
    │ └── js/ 
    │ └── scripts.js 
    ├── config/ 
    │ └── database.php 
    ├── controllers/ 
    │ ├── AuthController.php 
    │ ├── TrainingController.php 
    │ ├── ExerciseController.php 
    │ └── ExecutionController.php 
    ├── includes/ │ ├── header.php 
    │ ├── footer.php 
    │ └── navbar.php 
    ├── models/ 
    │ ├── User.php 
    │ ├── Exercise.php 
    ├── public/ 
    │ ├── index.php 
    │ ├── login.php 
    │ ├── cadastro.php 
    │ ├── dashboard.php 
    │ ├── training_detail.php 
    │ └── exercise_detail.php 
    ├── toasts/ 
    │ └── toast.php 
    └── README.md
 </pre>
---

## 📊 Progress Analysis
GymControll provides detailed visual feedback on your workout progression through interactive charts. Track your load increase and performance history over time using Chart.js.

---

## ✍️ Author

Developed by **Thomas Bastos**.

---

## 📄 License

This project is licensed under the MIT License. Feel free to use, modify, and distribute as needed.
