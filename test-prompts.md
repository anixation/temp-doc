Good catch — **testing is not yet covered** in the prompts above, but it absolutely should be, especially for a backend-heavy app like yours.

Let me provide you with **dedicated testing prompts** for both the **backend** and optionally the **frontend**, tailored for Cursor IDE and aligned with best practices for your FastAPI + EasyOCR project.

---

# ✅ BACKEND TESTING PROMPTS (Python / FastAPI)

---

### 1. `tests/test_api.py`

```python
# Create unit tests using pytest for the FastAPI API.
# Tests to include:
# - test_root_endpoint: ensure GET / returns 200 OK
# - test_upload_invoice: mock an image upload and assert correct OCR and response
# - test_get_invoices: insert dummy data and verify the GET /invoices/ returns expected structure
# Use FastAPI's TestClient for API testing.
```

---

### 2. `tests/test_parser.py`

```python
# Create unit tests for each function in parser.py:
# - test_extract_invoice_number
# - test_extract_invoice_date
# - test_extract_total_amount
# Use realistic OCR text samples and edge cases.
```

---

### 3. `tests/test_ocr.py`

```python
# Create a test for the OCR module:
# - Mock the EasyOCR reader and test that it returns expected extracted text
# - Validate that readtext() is called and result is parsed properly
```

---

### 4. `pytest.ini` or `pyproject.toml`

```ini
# Configure pytest to auto-discover tests in the tests/ directory
[pytest]
testpaths = tests
addopts = --disable-warnings
```

---

### 5. Testing Prompt for Cursor

```python
# Write a test suite for the FastAPI app using pytest and FastAPI TestClient.
# Include tests for API routes, OCR output (mocked), and parser logic.
# Use fixtures for clean database setup and teardown.
```

---

### Optional: Run tests inside Cursor terminal

```bash
pytest tests/
```

Or create a script in `Makefile`:

```makefile
test:
	pytest tests/
```

---

# 🧪 FRONTEND TESTING PROMPTS (Optional)

If you're using React and want basic testing:

---

### 6. `UploadForm.test.jsx`

```jsx
// Create a unit test for UploadForm using React Testing Library.
// Simulate file upload, mock fetch call, assert extracted text is shown.
```

---

### 7. `InvoiceList.test.jsx`

```jsx
// Write tests to:
// - Mock API call to fetchInvoices()
// - Render invoice rows
// - Check invoice data is displayed
```

---

### 8. Run frontend tests

```bash
npm test
```

---

### Frontend testing tools:

* [x] **React Testing Library**
* [x] **Jest** (comes with Create React App or Vite presets)

---

### ✅ Summary

| Area        | Tests Included? | Prompt Provided? |
| ----------- | --------------- | ---------------- |
| API routes  | ✅               | ✅                |
| OCR logic   | ✅ (mocked)      | ✅                |
| Parsing     | ✅               | ✅                |
| Frontend UI | Optional        | ✅                |

---

Would you like me to **generate the code** for `test_api.py` or mock an OCR test for you right now?
