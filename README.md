# 📚 FastAPI Library Management & External API Gateway

<p align="left">
  <img src="https://img.shields.io/badge/Python-3.10+-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/FastAPI-0.100+-009688?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI" />
  <img src="https://img.shields.io/badge/Pydantic-v2-E92063?style=flat-square&logo=pydantic&logoColor=white" alt="Pydantic" />
  <img src="https://img.shields.io/badge/Open_Library-API-333333?style=flat-square" alt="Open Library" />
  <img src="https://img.shields.io/badge/Docs-Swagger_UI-85EA2D?style=flat-square&logo=swagger&logoColor=black" alt="Swagger" />
</p>

> **Note:** Developed as a capstone project for the **Global AI Hub Python 202 Bootcamp**.

---

### 📖 Overview

A modular, multi-tier library management system demonstrating clean **Object-Oriented Programming (OOP)**, **External REST API Integration**, and modern **Asynchronous Web Service Development with FastAPI**.

The project bridges low-level terminal automation with production-style RESTful endpoints:
1. **Object-Oriented Core**: Encapsulated `Book` and `Library` domain models with persistent JSON file storage.
2. **External API Enrichment**: Queries the **Open Library REST API** using ISBN numbers to automatically fetch book metadata (title, author, publication date).
3. **FastAPI Web Service**: Complete CRUD REST endpoints backed by Pydantic request/response validation and interactive Swagger UI documentation.

---

### 🚀 Key Features

* **Dual Interface**: Operate via an interactive terminal CLI (`main.py`) or full HTTP REST API (`api.py`).
* **Automated ISBN Lookup**: Direct integration with Open Library API eliminates manual book data entry.
* **Data Persistence**: Automatic serialization and sync with local `library.json` database.
* **Auto-Generated Documentation**: Live interactive OpenAPI/Swagger specification at `/docs` and ReDoc at `/redoc`.

---

### 🛠️ API Reference

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `GET` | `/books` | List all books currently in the library catalog |
| `GET` | `/books/{isbn}` | Retrieve a specific book by its unique ISBN |
| `POST` | `/books` | Manually register a new book record |
| `POST` | `/books/from-api/{isbn}` | Automatically fetch and add book metadata via Open Library API |
| `PUT` | `/books/{isbn}` | Update existing book information |
| `DELETE` | `/books/{isbn}` | Delete a book record from the catalog |

#### Example Request Body (`POST /books`):

```json
{
  "eserAdı": "Simyacı",
  "yazar": "Paulo Coelho",
  "yayınTarihi": "1988",
  "isbn": "978-975-07-0130-3"
}
```

---

### 💻 Installation & Quickstart

#### 1. Clone the repository
```bash
git clone https://github.com/code-ex/fastapi-library-management.git
cd fastapi-library-management
```

#### 2. Install dependencies
```bash
pip install -r requirements.txt
```

#### 3. Run the Interactive CLI Menu
```bash
python main.py
```

#### 4. Run the FastAPI REST Server
```bash
uvicorn api:app --reload
```
Once the server is running, visit:
* **Interactive Swagger UI**: [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)
* **ReDoc Documentation**: [http://127.0.0.1:8000/redoc](http://127.0.0.1:8000/redoc)

---

### 📂 Project Structure

```
fastapi-library-management/
├── api.py           # FastAPI web application and REST endpoints
├── library.py       # Library collection logic and JSON persistence
├── book.py          # Book domain entity class
├── main.py          # Interactive terminal CLI application
├── library.json     # Persistent storage file for catalog records
├── requirements.txt # Project dependencies (FastAPI, Uvicorn, httpx, etc.)
└── .gitignore       # Git ignore rules
```

---

<sub>Developed by Mehmet Emin Metin • Global AI Hub Python 202 Bootcamp</sub>
