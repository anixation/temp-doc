Perfect — here are **step-by-step prompts** tailored for working in **Cursor IDE**, helping you build both the **backend (FastAPI + EasyOCR)** and **frontend (ReactJS or plain JS)** of your **invoice processing app** efficiently.

Each prompt is self-contained and written so you can copy it directly into Cursor as a comment above an empty file or block, and Cursor will know what to generate or autocomplete.

---

## 🧠 Project Structure (recommended in Cursor)

```
invoice-processor/
├── backend/
│   ├── main.py
│   ├── ocr.py
│   ├── parser.py
│   ├── database.py
│   ├── models.py
│   └── requirements.txt
├── frontend/
│   ├── public/
│   └── src/
│       ├── App.jsx
│       ├── UploadForm.jsx
│       ├── InvoiceList.jsx
│       └── api.js
└── .cursorrules
```

---

# 🧩 BACKEND PROMPTS (FastAPI + EasyOCR)

---

### 1. `main.py`

```python
# Build a FastAPI app with two endpoints:
# - POST /upload-invoice/: accepts an image file, uses EasyOCR to extract text, and stores extracted data in SQLite.
# - GET /invoices/: returns a list of all processed invoices with fields like invoice number, date, total.
# Use FastAPI's BackgroundTasks to run OCR in background.
# CORS should be enabled for localhost frontend access.
```

---

### 2. `ocr.py`

```python
# Create a utility function that uses EasyOCR to extract text from a given image file.
# Return both the raw OCR result and a joined string of text for further parsing.
```

---

### 3. `parser.py`

```python
# Write functions to extract structured fields from raw OCR text:
# - extract_invoice_number
# - extract_invoice_date
# - extract_total_amount
# Use regex or simple heuristics.
```

---

### 4. `models.py`

```python
# Define a Pydantic model (Invoice) for API response.
# Also define an ORM model (InvoiceORM) for SQLAlchemy with fields:
# - id, filename, extracted_text, invoice_number, date, total_amount, uploaded_at
```

---

### 5. `database.py`

```python
# Initialize SQLite using SQLAlchemy.
# Create a session dependency to be used in FastAPI endpoints.
# Include a method to create tables on startup.
```

---

### 6. `requirements.txt`

```txt
# List of all required Python packages
fastapi
uvicorn
easyocr
pillow
sqlalchemy
python-multipart
aiofiles
```

---

# 💻 FRONTEND PROMPTS (ReactJS)

Assume you're using Vite or Create React App.

---

### 1. `App.jsx`

```jsx
// Build a simple layout with:
// - UploadForm component for uploading invoices
// - InvoiceList component for displaying processed invoices
```

---

### 2. `UploadForm.jsx`

```jsx
// Create a React component with:
// - A file input field for image upload
// - Submit button
// - On submit, POST to /upload-invoice endpoint using fetch
// - Show loading state and display extracted text response
```

---

### 3. `InvoiceList.jsx`

```jsx
// Create a React component that:
// - Fetches invoice list from /invoices/ API
// - Displays each invoice's number, date, total, and upload time
// - Auto-refreshes on successful upload
```

---

### 4. `api.js`

```js
// Create helper functions for API calls:
// - uploadInvoice(file): POST to backend with FormData
// - fetchInvoices(): GET list of invoices
```

---

### 5. Add CORS to `main.py` (if not added)

```python
# Add CORS middleware to FastAPI to allow requests from localhost:3000 (React dev server)
```

---

### 6. `vite.config.js` or `package.json` (if using Create React App)

```js
// Set up proxy to backend running on localhost:8000
// so API requests go through the frontend dev server
```

---

# 🚀 Final Prompt (Optional)

```md
# Write a README.md file for the project with setup instructions:
# - How to install backend dependencies and run FastAPI with uvicorn
# - How to set up the frontend using npm/yarn
# - How to test OCR upload and see invoice list
# - Tech stack and features summary
```

---

Would you like me to generate the actual content for these files now, starting with backend or frontend?
