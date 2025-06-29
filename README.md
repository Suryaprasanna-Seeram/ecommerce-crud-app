# 🛒 E-commerce Product Management Web App

A full-stack CRUD web application built using **Node.js**, **Express**, **MySQL**, and **Vanilla JavaScript**. This app allows users to manage product categories and products, upload product data via Excel (`.xlsx`) files, and perform basic Create, Read, Update, and Delete operations.

---

## 📌 Project Features

### 🔹 1. Category Management
- Add new categories (name + description)
- Category name is **required** and must be **unique** (case-insensitive)
- View all existing categories in a table

### 🔹 2. Product Upload via Excel
- Upload an `.xlsx` file with sheet name: `Products`
- Columns required: `product_name`, `category_name`, `price`, `stock`
- Validates:
  - Category must exist
  - Price > 0
  - Stock ≥ 0
- Shows success message (e.g., ✅ Uploaded 3 products) or error (e.g., ❌ Row 2: Invalid category)

### 🔹 3. Product Display
- Displays all products with:
  - ID, Name, Category Name (via JOIN), Price, Stock
- Edit button to modify product details
- Delete button to remove a product

### 🔹 4. Product Editing
- Edit product name, category (dropdown), price, stock
- Validations on input (non-empty name, price > 0, etc.)

---

## 📊 Database Schema

### 📁 `category` Table

| Column         | Type             | Notes                        |
|----------------|------------------|------------------------------|
| category_id     | INT (PK, AI)     | Primary Key                  |
| category_name   | VARCHAR(255)     | Not Null, Unique             |
| description     | TEXT             | Optional                     |

---

### 📁 `product` Table

| Column         | Type             | Notes                        |
|----------------|------------------|------------------------------|
| product_id      | INT (PK, AI)     | Primary Key                  |
| product_name    | VARCHAR(255)     | Not Null                     |
| category_id     | INT (FK)         | Must reference category_id   |
| price           | DECIMAL(10,2)    | Must be > 0                  |
| stock           | INT              | Must be >= 0                 |

---

## 📥 Excel Upload Format

- File extension: `.xlsx`
- Sheet name: `Products`
- Columns:

| product_name | category_name | price | stock |
|--------------|---------------|-------|-------|
| Laptop       | Electronics   | 999.99| 20    |
| TV           | Electronics   | 599.99| 10    |

---

## 🛠️ Tech Stack

| Layer      | Technology         |
|------------|--------------------|
| Frontend   | HTML, CSS, JavaScript |
| Backend    | Node.js + Express |
| Database   | MySQL             |
| Excel Parser | xlsx (NPM package) |
| File Upload | multer (NPM package) |

---

## 🚀 Getting Started

### 1. Clone the repo

```bash
git clone https://github.com/Suryaprasanna-Seeram/ecommerce-crud-app.git
cd ecommerce-crud-app
### 2. Install dependencies  
   `npm install`

### 3. Set up your `.env` file:
   ```env
   DB_HOST=localhost
   DB_USER=root
   DB_PASSWORD=yourpassword
   DB_NAME=ecommerce_db
### 4. Start the server
node index.js

### 5. Open your browser:
http://localhost:3000

## 📂 Folder Structure

ecommerce-crud-app/
├── index.js                 # Entry point
├── db.js                    # MySQL config
├── /routes                  # API routes (category, product, upload)
│   ├── category.js
│   ├── product.js
│   └── upload.js
├── /public                  # Frontend (HTML, CSS, JS)
│   ├── index.html
│   ├── script.js
│   └── styles.css
├── /uploads                 # Temp Excel files
├── package.json
└── README.md

## 📦 Author
Surya Prasanna Seeram
Fresher Full Stack Developer — building and learning ❤️
