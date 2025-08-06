Great! You're working with **Cursor AI IDE**, limited to **JDK 17** on the backend (Java), and want to build a project:
👉 **"Backend for Intelligent API Response Mock Generator"**
with a **Java backend** and a **React.js frontend**.

This guide breaks down the **step-by-step prompts** you can paste into Cursor AI to develop your project incrementally. It's made for your limited setup — using only JDK 17 and Cursor.

---

## 🚀 Project Overview

You’re building a tool that:

* Accepts an OpenAPI/Swagger JSON or user-described API schema.
* Automatically generates intelligent mock responses for endpoints.
* Allows you to view and edit the mocked response via frontend.

---

## 🧠 Step-by-Step Prompts for Cursor AI

Each step is labeled for backend (🟤) or frontend (🔵).

---

### 🟤 Step 1: Initialize Java Backend Project

```
Create a minimal Spring Boot project with JDK 17, REST controllers, and no database for now. The project should include:
- `/api/mock/generate` POST endpoint which accepts an OpenAPI JSON (or schema description as plain text)
- Return mock JSON responses based on the input.
```

---

### 🟤 Step 2: Add JSON Parsing & Response Generator

```
Add logic to parse the OpenAPI schema or descriptive text to identify endpoint paths and expected response fields.

Generate mock responses using:
- Simple value mapping (e.g., string -> "example", number -> 42)
- Support nested objects and arrays.

Return a Map<String, Object> representing the generated JSON response.
```

---

### 🟤 Step 3: Add DTOs and Models

```
Create the necessary DTO classes:
- `MockRequest` with fields like `String schema` and `String format` (e.g., "openapi", "custom")
- `MockResponse` which wraps the mocked JSON as a string or object

Wire the DTOs into the POST `/api/mock/generate` endpoint.
```

---

### 🟤 Step 4: CORS & Dev Config

```
Enable CORS for all origins temporarily for React development.

Also, add a dev config to enable hot reload and allow access from localhost:3000.
```

---

### 🔵 Step 5: Create React App (without installing new software)

Since you cannot install Node.js directly:

```
Generate ReactJS frontend code (Vite or Create React App structure) with:
- A form to paste API schema
- A dropdown to select schema format (OpenAPI or custom)
- A submit button to call POST `/api/mock/generate`
- A panel to display the mock JSON response

Output the full structure as a downloadable zip (if possible), or display all key files:
- `App.jsx`
- `index.jsx`
- `package.json`
- `vite.config.js` or CRA `public/index.html`
```

---

### 🔵 Step 6: Implement Schema Form in React

```
Implement a React component called `MockForm` that:
- Has a textarea for schema input
- Has a dropdown for format ("openapi", "custom")
- Calls backend endpoint on submit using `fetch()`
- Displays the response JSON in a pretty-printed format
```

---

### 🔵 Step 7: Add Syntax Highlighting (Optional)

```
Add JSON pretty-print using a simple package like `react-json-view` or manually format using `JSON.stringify(res, null, 2)`.
If you can't install packages, build a basic expandable JSON viewer using vanilla JSX and CSS.
```

---

### 🟤 Step 8: Add Support for Custom Schema Description

```
Extend backend logic to accept schema description in simple text form (e.g., "User has name:string, age:number").

Parse this text and convert it into a JSON structure mock.

Support simple data types: string, number, boolean, array.
```

---

### 🟤 Step 9: Organize & Refactor Backend Code

```
Split logic into:
- `controller` for REST APIs
- `service` for generation logic
- `model` for DTOs

Add unit tests for the generator logic using JUnit (built into JDK 17).
```

---

### 🔵 Step 10: Add Copy & Export Features in React

```
Add buttons in the frontend:
- Copy generated JSON to clipboard
- Export response as `.json` file using a Blob
```

---

### 🔁 Bonus: Add History in Frontend (Optional)

```
Store previous mock results in browser localStorage with a timestamp.

Display a sidebar to view past mocks and click to re-load them into the viewer.
```

---

## 🧰 Tech Stack Summary

| Layer    | Technology                                       |
| -------- | ------------------------------------------------ |
| Frontend | React.js (vanilla JSX, fetch)                    |
| Backend  | Java 17, Spring Boot                             |
| IDE      | Cursor AI                                        |
| Server   | Self-host or local dev                           |
| Storage  | None (or optionally add JSON file storage later) |

---

## ✅ Next Steps

You can now copy-paste each step into Cursor AI and iterate safely.
If you'd like, I can **generate the starter backend or frontend code** for you next — just ask.

Would you like the actual Java Spring Boot boilerplate now?
