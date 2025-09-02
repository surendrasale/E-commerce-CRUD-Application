# Backend Developer Only Requirements for E-commerce Web App (CRUD) Test

## Objective
Build a backend for a web app to manage categories and products with Excel file upload and CRUD functionality. This test is for interns or students to demonstrate backend skills.

## Deadline
Complete as much as possible within 3 days from receiving the task.

## Database Schema

### Category Table
- **category_id**: Primary Key, Auto-increment, Integer
- **category_name**: Varchar(255), Not Null, Unique
- **description**: Text, Optional

### Products Table
- **product_id**: Primary Key, Auto-increment, Integer
- **product_name**: Varchar(255), Not Null
- **category_id**: Foreign Key to Category(category_id), Integer, Not Null
- **price**: Decimal(10,2), Not Null (e.g., 29.99)
- **stock**: Integer, Not Null (e.g., 100)

## Excel File Format
- **File Type**: `.xlsx`
- **Sheet Name**: "Products"
- **Columns**:
  - product_name (e.g., "Laptop")
  - category_name (e.g., "Electronics", must exist in Category table)
  - price (e.g., 999.99)
  - stock (e.g., 50)

## Functional Requirements
1. **Category Management**:
   - API endpoint to create a category (POST /categories, fields: category_name, description).
   - Validate: category_name not empty, unique (case-insensitive).
   - API endpoint to list categories (GET /categories).
2. **Excel Upload**:
   - API endpoint to upload `.xlsx` file (POST /upload).
   - Read "Products" sheet, insert into Products table:
     - Match category_name to category_id (must exist).
     - Validate: price > 0, stock >= 0, category_name exists.
   - Return success (e.g., "Uploaded 5 products") or error (e.g., "Row 2: Invalid price").
3. **Data Retrieval**:
   - API endpoint for products (GET /products, include category_name via join).
4. **Edit Products**:
   - API endpoint to update a product (PUT /products/:id, fields: product_name, category_id, price, stock).
   - Validate: product_name not empty, price > 0, stock >= 0, category_id valid.

## Technical Requirements
- **Backend**: Use a beginner-friendly framework:
  - Python (Flask, FastAPI)
  - Node.js (Express)
  - PHP (Laravel)
- **Database**: SQLite, MySQL, or PostgreSQL.
- **Validation**: Validate inputs and Excel data. Return clear error messages.
- **Security**: Restrict to `.xlsx` files, limit file size (5MB), sanitize inputs.
- **Frontend**: Not required. A basic HTML form for testing APIs is optional.

## Deliverables
1. **Source Code**: Backend code in a Git repository or ZIP file.
2. **SQL File**: `schema.sql` (CREATE TABLE for Category, Products) and `data.sql` (3 categories, 5 products).
3. **Sample Excel File**: `sample.xlsx` with 5-10 rows in Products sheet.
4. **README.md**:
   - Setup: Install dependencies, database setup.
   - Run: Command to start server (e.g., `flask run`).
   - API endpoints: List endpoints (e.g., POST /categories).
   - Excel format: Explain Products sheet.
   - Limitations: Note incomplete features.

## Tips
- Focus on APIs and database logic.
- Use Postman to test endpoints.
- Prioritize: Database, category APIs, Excel upload, product update.