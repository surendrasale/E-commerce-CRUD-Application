# Frontend Developer Only Requirements for E-commerce Web App (CRUD) Test

## Objective
Build a frontend for a web app to manage categories and products, with Excel file upload and CRUD functionality. Store data in **local storage** to retain state across page refreshes. This test is for interns or students.

## Deadline
Complete as much as possible within 3 days from receiving the task.

## Functional Requirements
1. **Category Management**:
   - Form to add a category (category_name, description).
   - Validate: category_name not empty, unique (case-insensitive).
   - Table to display categories (category_id, category_name, description).
2. **Excel Upload**:
   - Form to upload an `.xlsx` file.
   - Display success (e.g., "Uploaded 5 products") or error (e.g., "Row 2: Invalid price") from backend or mock processing.
3. **Data Display**:
   - Categories table: category_id, category_name, description.
   - Products table: product_id, product_name, category_name, price, stock.
4. **Edit Products**:
   - "Edit" button per product row.
   - Form to update product_name, category_id (dropdown), price, stock.
   - Validate: product_name not empty, price > 0, stock >= 0, category_id valid.

## Technical Requirements
- **Frontend Framework**: Build a new UI from scratch using:
  - React, Vue, Next.js, or Angular (preferred).
  - Plain HTML/CSS/JS acceptable for beginners.
- **Local Storage**:
  - Store categories and products in `localStorage` to persist data.
  - On page load, retrieve data from `localStorage` to retain state.
  - Update `localStorage` on add/edit operations.
  - Example structure:
    ```json
    {
      "categories": [
        { "category_id": 1, "category_name": "Electronics", "description": "Gadgets" }
      ],
      "products": [
        { "product_id": 1, "product_name": "Laptop", "category_id": 1, "price": 999.99, "stock": 50 }
      ]
    }
    ```
- **State Management**: Use React `useState`, Vuex, or similar, synced with `localStorage`.
- **API Integration**: Connect to backend APIs or use mock APIs for CRUD.
- **Validation**: Show backend or mock error messages clearly.
- **Design**: Create a clean, user-friendly UI with Bootstrap or Tailwind.

## Deliverables
1. **Source Code**: Frontend code (e.g., React, Vue) in a Git repository or ZIP file.
2. **README.md**:
   - Setup: Install dependencies (e.g., `npm install`).
   - Run: Command to start frontend (e.g., `npm start`).
   - Local Storage: Explain data storage/retrieval.
   - API Requirements: List expected endpoints or mock data.
   - Excel Upload: Note how upload is handled.
   - Limitations: List incomplete features.

## Tips
- Prioritize: `localStorage` setup, category form, tables, edit form, upload feedback.
- Use `JSON.stringify()` to save and `JSON.parse()` to load `localStorage` data.
- Mock APIs with static JSON if no backend.
- Test state retention by refreshing the page.
- Keep UI simple but functional.