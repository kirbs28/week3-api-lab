### **README.md - API Development & Microservices**  

# **API Development & Microservices - Week 3 Lab**  

## **Project Overview**  
This project is a RESTful API that demonstrates user authentication and product management using **Node.js, Express, and JWT authentication**. The API is designed using a **microservices architecture**, where authentication and product management are handled as separate services.  

## **Features**  
- User Registration and Login using **JWT (JSON Web Token)**  
- Secure **protected routes** requiring authentication  
- Microservices architecture with **separate authentication & product services**  
- API endpoints tested using **Postman**  

---

## **Tech Stack**  
- **Backend:** Node.js, Express.js  
- **Authentication:** JWT (JSON Web Tokens), bcrypt.js  
- **Data Handling:** Express JSON Middleware  
- **API Testing:** Postman  

---

## **Project Structure**  
```
week3-api-lab/
├── auth-service.js         # Handles user authentication (register, login)
├── product-service.js      # Manages product data (fetch products)
├── .env                    # Environment variables (optional)
├── package.json            # Project dependencies
├── README.md               # API Documentation
```

---

## **Installation & Setup**  

### **1️. Prerequisites**  
- Install **Node.js** (LTS version)  
- Install **Postman** (for API testing)  

### **2️. Clone the Repository**  
```sh
git clone https://github.com/your-repo/week3-api-lab.git
cd week3-api-lab
```

### **3️. Install Dependencies**  
```sh
npm install express jsonwebtoken bcryptjs dotenv
```

---

## **Running the Microservices**  

### **1️. Start the Authentication Service (`auth-service.js`)**  
```sh
node auth-service.js
```
✅ Server should run on **PORT 4000**.

### **2️. Start the Product Service (`product-service.js`)**  
```sh
node product-service.js
```
✅ Server should run on **PORT 5000**.

---

## **API Endpoints**  

### **1️. User Authentication Service (`auth-service.js`)**  
| Method | Endpoint         | Description                 |
|--------|----------------|-----------------------------|
| POST   | `/api/register` | Register a new user        |
| POST   | `/api/login`    | Login and receive a JWT    |

#### **📌 Example Register Request (POST `/api/register`)**  
**URL:** `http://localhost:4000/api/register`  
**Headers:** `Content-Type: application/json`  
**Body (JSON):**
```json
{
  "username": "testuser",
  "password": "password123"
}
```
✅ **Expected Response:**
```json
{
  "message": "User registered successfully"
}
```

#### **📌 Example Login Request (POST `/api/login`)**  
**URL:** `http://localhost:4000/api/login`  
**Headers:** `Content-Type: application/json`  
**Body (JSON):**
```json
{
  "username": "testuser",
  "password": "password123"
}
```
✅ **Expected Response:** (Copy the `token`)
```json
{
  "token": "your-jwt-token"
}
```

---

### **2️. Product Management Service (`product-service.js`)**  
| Method | Endpoint          | Description           |
|--------|-----------------|-----------------------|
| GET    | `/api/products` | Fetch all products   |

#### **📌 Example Get Products Request (GET `/api/products`)**  
**URL:** `http://localhost:5000/api/products`  
✅ **Expected Response:**
```json
[
  { "id": 1, "name": "Laptop" },
  { "id": 2, "name": "Phone" }
]
```

---

## **Testing with Postman**  

### **1️. User Authentication**  
✅ **Register** → `http://localhost:4000/api/register`  
✅ **Login** → `http://localhost:4000/api/login` (Copy JWT Token)  

### **2️. Fetch Products**  
✅ **Get Products** → `http://localhost:5000/api/products`  
