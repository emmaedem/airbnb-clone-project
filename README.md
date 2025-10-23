# 🏠 Airbnb Clone Project

## 🚀 Overview
The Airbnb Clone backend project is built to replicate the essential features of Airbnb — including user authentication, property management, bookings, payments, and reviews.

## 🎯 Project Goals
- Implement a secure **user authentication** system (signup/login)
- Develop **property listing** and **booking** features
- Integrate **payment processing**
- Create a **review and rating** system
- Optimize data storage and retrieval

## ⚙️ Technology Stack

This project uses a combination of modern backend technologies to build a secure, scalable, and high-performing system for managing users, properties, bookings, and payments.

### 🧱 Backend Framework
**Django:** A powerful Python web framework used to build the main backend logic, handle routing, and manage data between the frontend and the database.

### 🔌 API Layer
**Django REST Framework (DRF):** Extends Django to easily create RESTful APIs — allowing the frontend to communicate with the backend using HTTP requests.  
**GraphQL:** Provides a flexible way for clients to query and retrieve exactly the data they need from the backend.

### 🗄️ Database
**PostgreSQL:** A robust and reliable relational database used to store user data, property listings, bookings, and payment details. It ensures data consistency and supports advanced queries.

### ⚙️ Task Management & Background Jobs
**Celery:** Handles background tasks such as sending notifications or processing payments without slowing down the main application.  
**Redis:** Works with Celery as a message broker and is also used for caching frequently requested data to improve performance.

### 🐳 Containerization & Deployment
**Docker:** Packages the application and all its dependencies into containers, ensuring the project runs consistently across different environments (local and cloud).  
**CI/CD Pipelines:** Automates testing and deployment so that new code changes are safely released without manual intervention.

### 🌐 API Documentation
**OpenAPI / Swagger:** Automatically documents all API endpoints, making it easier for developers and testers to understand and interact with the backend.

---

Together, these technologies power the Airbnb Clone backend — ensuring reliability, scalability, and smooth user experience.


## 🗄️ Database Design

The database is designed to store and manage all core data for the Airbnb Clone project — including users, properties, bookings, reviews, and payments.  
Each entity is represented as a database table, with relationships connecting them to reflect real-world interactions between hosts, guests, and properties.

---

### 👤 Users
Represents both guests and hosts on the platform.

**Key Fields:**
- `id`: Unique identifier for each user.
- `name`: Full name of the user.
- `email`: User’s email address (used for login/authentication).
- `password`: Encrypted password.
- `role`: Defines whether the user is a host or a guest.

**Relationships:**
- A **user** can list multiple **properties**.
- A **user** can make multiple **bookings**.
- A **user** can write multiple **reviews**.

---

### 🏠 Properties
Represents the houses, apartments, or rooms listed by hosts.

**Key Fields:**
- `id`: Unique identifier for each property.
- `user_id`: References the host (User who owns the property).
- `title`: Name or short description of the property.
- `location`: Address or city where the property is located.
- `price_per_night`: Cost per night of stay.

**Relationships:**
- A **property** belongs to a **user** (host).
- A **property** can have multiple **bookings**.
- A **property** can have multiple **reviews**.

---

### 📅 Bookings
Represents reservations made by users for specific properties.

**Key Fields:**
- `id`: Unique identifier for each booking.
- `user_id`: References the guest who made the booking.
- `property_id`: References the booked property.
- `check_in_date`: Start date of the booking.
- `check_out_date`: End date of the booking.

**Relationships:**
- A **booking** belongs to a **user** (guest).
- A **booking** belongs to a **property**.
- A **booking** may have one **payment** record.

---

### 💳 Payments
Represents payment transactions related to bookings.

**Key Fields:**
- `id`: Unique identifier for each payment.
- `booking_id`: References the related booking.
- `amount`: Total payment amount.
- `payment_status`: Indicates if the payment was successful or pending.
- `payment_date`: When the payment was processed.

**Relationships:**
- A **payment** belongs to a **booking**.
- A **booking** can have one **payment**.

---

### ⭐ Reviews
Represents user feedback about properties.

**Key Fields:**
- `id`: Unique identifier for each review.
- `user_id`: References the user who wrote the review.
- `property_id`: References the property being reviewed.
- `rating`: Numeric score (e.g., 1–5 stars).
- `comment`: User’s written feedback.

**Relationships:**
- A **review** belongs to a **user**.
- A **review** belongs to a **property**.

---

### 🔗 Entity Relationships Summary

| Entity | Relationship |
|---------|---------------|
| User → Property | One-to-Many (A user can list multiple properties) |
| User → Booking | One-to-Many (A user can make multiple bookings) |
| Property → Booking | One-to-Many (A property can be booked multiple times) |
| Booking → Payment | One-to-One (Each booking has one payment) |
| Property → Review | One-to-Many (A property can have multiple reviews) |
| User → Review | One-to-Many (A user can write multiple reviews) |

---

### 🧭 Summary
This relational design ensures that:
- Data remains organized and consistent.  
- Relationships mirror real-world connections (guests, hosts, bookings, etc.).  
- Queries for user bookings, property reviews, or payments can be made efficiently.



## 👥 Team Roles

### 🧑🏽‍💻 Backend Developer
Responsible for building and maintaining the backend logic of the application.  
Implements API endpoints for user management, property listings, bookings, payments, and reviews.  
Ensures data flow between the database and frontend is efficient and secure.

### 🗄️ Database Administrator (DBA)
Designs, implements, and manages the database structure.  
Creates tables and relationships (e.g., linking users, bookings, and properties).  
Optimizes queries, manages indexing, backups, and ensures data integrity.

### ⚙️ DevOps Engineer
Sets up the development and deployment environment using tools like Docker, Redis, and CI/CD pipelines.  
Manages the app’s hosting, scalability, monitoring, and continuous integration processes.

### 🧪 QA Engineer (Quality Assurance)
Tests the APIs and backend features to make sure everything works as expected.  
Creates and runs test cases to detect bugs, security issues, or broken logic before deployment.

### 🎨 Frontend Developer (optional)
Integrates the backend APIs into a user interface (using React, Vue, or any frontend framework).  
Ensures the data from the backend is displayed correctly and that users can interact smoothly with the app.

### 👑 Project Manager
Oversees the project progress, sets timelines, and ensures effective communication between all roles.  
Tracks milestones, manages deliverables, and helps the team stay focused on the objectives.

---

_Note: During this learning project, all roles are performed by a single developer — **Edem Emmanuel Etim**._


## 👥 Author
**Edem Emmanuel Etim**
- Backend Developer (Prodev Backend Program)
- [LinkedIn](https://linkedin.com/in/emmaedem86)
- [GitHub](https://github.com/emmaedem86)
