# 📸 Cam Reserve - Smart Camera Booking System

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-00000F?style=for-the-badge&logo=mysql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Hibernate](https://img.shields.io/badge/Hibernate-59666C?style=for-the-badge&logo=hibernate&logoColor=white)

> **"Lights. Camera. Book!"**

**Cam Reserve** is a comprehensive full-stack web application designed to digitize and automate the camera rental workflow. Tailored for photography enthusiasts and rental businesses, it streamlines equipment booking, inventory management, and even supports **Live Streaming** for events.

---

## 🚀 Project Overview

In the traditional rental industry, manual logs and phone bookings lead to errors. **Cam Reserve** solves this by providing:
* **For Users:** A seamless interface to browse equipment, check real-time availability, and book cameras for specific dates.
* **For Admins:** A powerful dashboard to manage inventory, approve/reject requests, and monitor user activity.
* **Live Tech:** Integration with **Kurento Media Server** via Docker to enable live event streaming capabilities directly from the platform.

---

## 🌟 Key Features

### 👤 User Panel
* **Secure Authentication:** User registration and encrypted login.
* **Smart Booking Engine:** Browse cameras, select dates, and receive immediate conflict validation (preventing double bookings).
* **Booking History:** Track status of past and upcoming reservations (Pending/Approved/Rejected).
* **Live Streaming:** Join event streams using a unique **Stream ID**.

### 🛡️ Admin Dashboard
* **Inventory Management:** Add/Remove cameras and update specifications.
* **Booking Workflow:** Real-time approval or rejection of user booking requests.
* **User Management:** Monitor registered users and manage admin access roles.
* **Stream Management:** Generate Stream IDs for live broadcasting.

---

## 🛠️ Technical Architecture

This project follows the **MVC (Model-View-Controller)** architecture and adheres to RESTful API principles.

| Layer | Technologies Used |
| :--- | :--- |
| **Frontend** | HTML5, CSS3, JavaScript (Responsive UI) |
| **Backend** | Java (JDK 17+), Spring Boot 3.x |
| **Database** | MySQL (Relational Data Storage) |
| **ORM** | Hibernate (JPA) for Object-Relational Mapping |
| **DevOps** | Docker (Containerization for Media Server) |
| **Streaming** | WebRTC, Kurento Media Server |
| **Communication**| JavaMail Sender (SMTP for Email Confirmations) |

---

## 📂 Project Structure

The repository is divided into two main modules:

1.  **`Camera_booking_backendend-main`**: Contains the Spring Boot server code, API controllers, Services, and Repositories.
2.  **`Camera_Booking-main`**: Contains the Frontend static assets (HTML/CSS/JS) that consume the backend APIs.

---

## ⚙️ Installation & Setup Guide

### Prerequisites
* Java Development Kit (JDK) 11 or higher
* MySQL Server installed and running
* Docker Desktop (for Live Streaming features)
* IDE (IntelliJ IDEA, Eclipse, or VS Code)

### Step 1: Database Configuration
1.  Open MySQL Workbench and create a database named `cam_reserve`.
2.  Update the `application.properties` file in the backend folder:
    ```properties
    spring.datasource.url=jdbc:mysql://localhost:3306/cam_reserve
    spring.datasource.username=root
    spring.datasource.password=YOUR_PASSWORD
    spring.jpa.hibernate.ddl-auto=update
    ```

### Step 2: Run the Backend
1.  Navigate to `Camera_booking_backendend-main`.
2.  Run the Spring Boot application (Main class).
3.  The server will start on `http://localhost:8080`.

### Step 3: Run the Media Server (Docker) To enable the live streaming features, you must run the Kurento Media Server using Docker:
```bash
docker run --rm -p 8888:8888 kurento/kurento-media-server:latest
