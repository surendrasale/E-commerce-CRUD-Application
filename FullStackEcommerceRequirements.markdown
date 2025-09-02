# Full Stack Developer Requirements for E-commerce Web App (CRUD) Test

## Objective
Build a web app to manage categories and products with Excel file upload and basic CRUD (Create, Read, Update) functionality. This test is for interns or students to demonstrate full stack skills.

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
   - Form to add a category (category_name, description).
   - Validate: category_name not empty, unique (case-insensitive).
   - Display categories in a table (category_id, category_name, description).
2. **Excel Upload**:
   - Form to upload `.xlsx` file.
   - Read "Products" sheet, insert into Products table:
     - Match category_name to category_id (must exist).
     - Validate: price > 0, stock >= 0, category_name exists.
   - Show success (e.g., "Uploaded 5 products") or error (e.g., "Row 2: Invalid price").
3. **Data Display**:
   - Categories table: category_id, category_name, description.
   - Products table: product_id, product_name, category_name (via join), price, stock.
4. **Edit Products**:
   - "Edit" button per product row.
   - Form to update product_name, category_id (dropdown), price, stock.
   - Validate: product_name not empty, price > 0, stock >= 0, category_id valid.

## Technical Requirements
- **Backend**: Use a beginner-friendly framework:
  - Python (Flask, Django, FastAPI)
  - Node.js (Express)
  - PHP (Laravel)
- **Database**: SQLite, MySQL, or PostgreSQL.
- **Frontend**: HTML, CSS, JavaScript. Optional: React, Vue, or Next.js.
- **Validation**: Check all inputs and Excel data. Show clear error messages.
- **Security**: Allow only `.xlsx` files, limit file size (5MB), sanitize inputs.
- **Design**: Not a priority. Use provided HTML templates in the repository or create a basic UI (custom UI earns extra points).

## Deliverables
1. **Source Code**: Backend and frontend code in a Git repository or ZIP file.
2. **SQL File**: `schema.sql` (CREATE TABLE for Category, Products) and `data.sql` (3 categories, 5 products).
3. **Sample Excel File**: `sample.xlsx` with 5-10 rows in Products sheet.
4. **README.md**:
   - Setup: Install dependencies (e.g., `npm install`, `pip install -r requirements.txt`), database setup.
   - Run: Commands (e.g., `flask run`, `node app.js`).
   - Excel format: Explain Products sheet.
   - Limitations: Note incomplete features.

## Tips
- Prioritize: Database setup, category form, Excel upload, product table/edit.
- Use templates to save time on UI.
- Test Excel upload with a small file (5 rows).