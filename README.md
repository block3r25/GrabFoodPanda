# 🍔 GrubFoodPanda

**GrubFoodPanda** is a modern food delivery application that connects customers with restaurants and delivery riders through a convenient online platform. Users can browse restaurants, explore menus, place orders, track deliveries, and manage their accounts from a single application.

> A full-featured food delivery platform inspired by popular services such as GrabFood and foodpanda.

---

## 📋 Table of Contents

* [Features](#-features)
* [System Overview](#-system-overview)
* [User Roles](#-user-roles)
* [Application Flow](#-application-flow)
* [Technology Stack](#-technology-stack)
* [Project Structure](#-project-structure)
* [Installation](#-installation)
* [Configuration](#-configuration)
* [Database](#-database)
* [API](#-api)
* [Screenshots](#-screenshots)
* [Security](#-security)
* [Future Improvements](#-future-improvements)
* [Contributing](#-contributing)
* [License](#-license)

---

## 🚀 Features

### 👤 Customer

* User registration and authentication
* Browse nearby restaurants
* Search restaurants and food items
* Filter by cuisine, category, price, and rating
* View restaurant information
* Browse menus and food items
* Customize food orders
* Add items to cart
* Apply discounts and vouchers
* Place orders
* Select delivery address
* Select payment method
* View order history
* Track order status
* Rate restaurants and food
* Rate delivery riders
* Manage profile and addresses

### 🏪 Restaurant

* Restaurant registration and management
* Restaurant profile management
* Menu management
* Add, edit, and remove food items
* Set food availability
* Manage incoming orders
* Accept or reject orders
* Update order preparation status
* View sales reports
* Manage restaurant operating hours

### 🛵 Delivery Rider

* Rider registration
* Rider profile
* Online/offline availability
* Receive delivery requests
* Accept delivery assignments
* View pickup location
* View customer delivery location
* Update delivery status
* Delivery history
* Earnings tracking

### 🛠️ Administrator

* Dashboard
* User management
* Restaurant management
* Rider management
* Order management
* Category management
* Voucher and promotion management
* Payment monitoring
* Reports and analytics
* System configuration
* Audit logs

---

## 🏗️ System Overview

```text
                    ┌─────────────────────┐
                    │      Customer       │
                    │   Web / Mobile App  │
                    └──────────┬──────────┘
                               │
                               ▼
┌──────────────┐      ┌─────────────────────┐
│  Restaurant  │─────▶│     REST API        │
│   Portal     │      │   Backend Server     │
└──────────────┘      └──────────┬──────────┘
                                  │
┌──────────────┐                  │
│ Rider Portal │──────────────────┤
└──────────────┘                  │
                                  ▼
                         ┌─────────────────┐
                         │    Database     │
                         │     MySQL       │
                         └─────────────────┘
                                  │
                    ┌─────────────┼─────────────┐
                    ▼             ▼             ▼
               Payments      Maps/GPS      Notifications
```

---

## 👥 User Roles

| Role              | Description                           |
| ----------------- | ------------------------------------- |
| **Customer**      | Orders food and tracks deliveries     |
| **Restaurant**    | Manages menus and customer orders     |
| **Rider**         | Picks up and delivers customer orders |
| **Administrator** | Manages the entire platform           |

---

## 🔄 Application Flow

### Customer Order

```text
Login
  ↓
Browse Restaurants
  ↓
Select Restaurant
  ↓
Select Food
  ↓
Add to Cart
  ↓
Checkout
  ↓
Select Address & Payment
  ↓
Place Order
  ↓
Restaurant Accepts Order
  ↓
Food Preparation
  ↓
Rider Assigned
  ↓
Food Picked Up
  ↓
Delivery
  ↓
Order Completed
  ↓
Customer Rating
```

### Order Status

```text
PENDING
   ↓
CONFIRMED
   ↓
PREPARING
   ↓
READY_FOR_PICKUP
   ↓
RIDER_ASSIGNED
   ↓
PICKED_UP
   ↓
OUT_FOR_DELIVERY
   ↓
DELIVERED
```

---

## 💻 Technology Stack

The application can be implemented using the following technologies:

### Frontend

* HTML5
* CSS3
* JavaScript
* Bootstrap
* AJAX
* Responsive Web Design

### Backend

* PHP
* RESTful API
* MySQL
* JSON

### Infrastructure

* Linux Server
* Apache/Nginx
* SSL/TLS
* Cloudflare
* Git/GitHub

### Integrations

* Google Maps API
* Payment Gateway
* SMS/Email Notifications
* Push Notifications

---

## 📁 Project Structure

```text
grubfoodpanda/
│
├── api/
│   ├── auth/
│   ├── users/
│   ├── restaurants/
│   ├── menu/
│   ├── orders/
│   ├── riders/
│   ├── payments/
│   └── notifications/
│
├── admin/
│   ├── dashboard.php
│   ├── users.php
│   ├── restaurants.php
│   ├── riders.php
│   ├── orders.php
│   └── reports.php
│
├── customer/
│   ├── index.php
│   ├── restaurants.php
│   ├── menu.php
│   ├── cart.php
│   ├── checkout.php
│   └── orders.php
│
├── restaurant/
│   ├── dashboard.php
│   ├── menu.php
│   ├── orders.php
│   └── reports.php
│
├── rider/
│   ├── dashboard.php
│   ├── deliveries.php
│   ├── earnings.php
│   └── profile.php
│
├── assets/
│   ├── css/
│   ├── js/
│   ├── images/
│   └── fonts/
│
├── config/
│   ├── database.php
│   └── config.php
│
├── uploads/
│   ├── restaurants/
│   ├── food/
│   └── profiles/
│
├── .htaccess
├── .gitignore
├── README.md
└── index.php
```

---

## ⚙️ Installation

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/grubfoodpanda.git
cd grubfoodpanda
```

### 2. Create the Database

Create a MySQL database:

```sql
CREATE DATABASE grubfoodpanda;
```

Import the database structure:

```bash
mysql -u root -p grubfoodpanda < database.sql
```

### 3. Configure Database

Update:

```text
config/database.php
```

Example:

```php
<?php

$host = "localhost";
$dbname = "grubfoodpanda";
$username = "root";
$password = "";

$conn = new mysqli(
    $host,
    $username,
    $password,
    $dbname
);

if ($conn->connect_error) {
    die("Database connection failed.");
}
```

### 4. Configure the Web Server

Point the web server document root to:

```text
/grubfoodpanda/
```

For Apache:

```text
DocumentRoot /var/www/html/grubfoodpanda
```

### 5. Set Permissions

```bash
chmod -R 755 grubfoodpanda
chmod -R 775 grubfoodpanda/uploads
```

### 6. Open the Application

```text
http://localhost/grubfoodpanda
```

---

## 🗄️ Database

Core database entities include:

```text
users
 ├── customers
 ├── restaurant_users
 └── riders

restaurants
 ├── restaurant_categories
 ├── menu_categories
 └── menu_items

orders
 ├── order_items
 ├── order_status
 └── delivery_assignments

payments
addresses
reviews
ratings
vouchers
notifications
```

### Main Tables

| Table                  | Purpose                      |
| ---------------------- | ---------------------------- |
| `users`                | User accounts                |
| `restaurants`          | Restaurant information       |
| `menu_categories`      | Food categories              |
| `menu_items`           | Restaurant food/menu         |
| `orders`               | Customer orders              |
| `order_items`          | Individual items in an order |
| `riders`               | Delivery rider information   |
| `delivery_assignments` | Rider/order assignments      |
| `payments`             | Payment transactions         |
| `addresses`            | Customer delivery addresses  |
| `reviews`              | Customer reviews             |
| `vouchers`             | Discounts and promotions     |
| `notifications`        | System notifications         |

---

## 🔌 API

The application exposes REST-style endpoints.

### Authentication

```text
POST /api/auth/login
POST /api/auth/register
POST /api/auth/logout
```

### Restaurants

```text
GET  /api/restaurants
GET  /api/restaurants/{id}
POST /api/restaurants
PUT  /api/restaurants/{id}
```

### Menu

```text
GET    /api/restaurants/{id}/menu
POST   /api/menu
PUT    /api/menu/{id}
DELETE /api/menu/{id}
```

### Orders

```text
POST /api/orders
GET  /api/orders/{id}
PUT  /api/orders/{id}/status
GET  /api/orders/customer/{id}
```

### Delivery

```text
GET  /api/riders/available
POST /api/delivery/assign
PUT  /api/delivery/{id}/status
```

---

## 🔐 Security

The application should implement the following security controls:

* Password hashing using `password_hash()`
* Prepared SQL statements
* Session security
* CSRF protection
* Input validation and sanitization
* Output escaping
* Role-based access control
* API authentication
* Rate limiting
* Secure file uploads
* HTTPS/TLS
* Secure HTTP headers
* Audit logging
* Database backups

**Never commit credentials, API keys, database passwords, or `.env` files to GitHub.**

Example `.gitignore`:

```gitignore
.env
config/database.php
uploads/*
*.log
.DS_Store
```

---

## 💳 Payment Architecture

The payment module can support multiple payment methods:

```text
Customer
   │
   ▼
Checkout
   │
   ├── Cash on Delivery
   │
   ├── GCash
   │
   ├── Maya
   │
   └── Online Payment Gateway
            │
            ▼
      Payment Provider
            │
            ▼
      Payment Callback
            │
            ▼
      Update Order Status
```

Payment credentials should always be stored outside the source repository.

---

## 📍 Delivery Tracking

The rider application can periodically send GPS coordinates:

```text
Rider App
    │
    │ latitude / longitude
    ▼
Tracking API
    │
    ▼
Database / Cache
    │
    ▼
Customer Tracking Page
```

The customer can then see:

* Rider location
* Delivery status
* Estimated delivery time
* Restaurant location
* Delivery destination

---

## 📸 Screenshots

Add application screenshots here:

```text
docs/
├── login.png
├── customer-dashboard.png
├── restaurant-menu.png
├── cart.png
├── checkout.png
├── order-tracking.png
├── restaurant-dashboard.png
├── rider-dashboard.png
└── admin-dashboard.png
```

Example:

```markdown
![Customer Dashboard](docs/customer-dashboard.png)
```

---

## 🧪 Testing

Before deployment, test the following workflows:

```text
✓ User Registration
✓ User Login
✓ Restaurant Registration
✓ Menu Management
✓ Cart Management
✓ Checkout
✓ Order Creation
✓ Restaurant Order Acceptance
✓ Rider Assignment
✓ Delivery Status Updates
✓ Payment Processing
✓ Order Cancellation
✓ Reviews & Ratings
✓ Notifications
✓ Role-Based Access
```

---

## 🛣️ Future Improvements

* [ ] Android mobile application
* [ ] iOS mobile application
* [ ] Real-time rider tracking
* [ ] Push notifications
* [ ] GCash integration
* [ ] Maya integration
* [ ] AI-powered food recommendations
* [ ] Restaurant analytics
* [ ] Dynamic delivery fees
* [ ] Loyalty/rewards system
* [ ] Referral system
* [ ] Scheduled orders
* [ ] Multi-restaurant ordering
* [ ] Advanced delivery route optimization
* [ ] Real-time order chat
* [ ] Customer support/ticketing system

---

## 🤝 Contributing

Contributions are welcome.

1. Fork the repository.
2. Create a feature branch.

```bash
git checkout -b feature/new-feature
```

3. Commit your changes.

```bash
git commit -m "Add new feature"
```

4. Push the branch.

```bash
git push origin feature/new-feature
```

5. Open a Pull Request.

---

## 📄 License

This project is released under the **MIT License**.

See the `LICENSE` file for details.

---

## 👨‍💻 Project

**GrubFoodPanda — Food Delivery Platform**

A food ordering and delivery management system designed to connect **customers, restaurants, and delivery riders** through a unified digital platform.

```text
Customers ───────┐
                 │
Restaurants ─────┼──► GrubFoodPanda ◄── Delivery Riders
                 │
Administrators ──┘
```

⭐ If you find this project useful, consider giving the repository a **star**.
