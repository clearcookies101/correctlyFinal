# 🧠 Correctly API – AI-Powered Autocorrect Backend

Correctly API is a **FastAPI-based backend** that provides intelligent text autocorrection using **SymSpell**.
It accepts text input, corrects spelling mistakes, and returns the corrected version with detailed metadata such as number of corrections and processing time.



## 🚀 Features

✅ Built with **FastAPI**
✅ Uses **SymSpell** for fast and accurate spell correction
✅ Provides structured JSON responses
✅ Includes **CORS middleware** for frontend integration
✅ Organized into modular components (routes, services, models, utils)
✅ Ready for deployment (Docker / Render / Railway)



## 📁 Project Structure

```
correctly_api/
│
├── app/
│   ├── main.py                  # App entry file
│   ├── core/
│   │   └── symspell_loader.py   # Loads and initializes SymSpell dictionary
│   ├── models/
│   │   └── correction_models.py # Request/Response data models
│   ├── routes/
│   │   └── correction_route.py  # API endpoints
│   ├── services/
│   │   └── correction_service.py# Business logic for text correction
│   └── utils/
│       └── text_utils.py        # Helper functions for text correction
│
├── requirements.txt             # Python dependencies
└── run.py                       # Uvicorn startup script
```



## 🛠️ Setup & Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/correctly-api.git
cd correctly-api
```

### 2. Create Virtual Environment

```bash
python -m venv venv
```

Activate it:

#### On Windows:

```bash
venv\Scripts\activate
```

#### On macOS/Linux:

```bash
source venv/bin/activate
```



### 3. Install Dependencies

```bash
pip install -r requirements.txt
```



### 4. Run the Server

```bash
python run.py
```

Server will start at:
👉 **[http://127.0.0.1:8000](http://127.0.0.1:8000)**



## 🌐 API Endpoints

### **GET /**

**Description:** Basic welcome route
**Response:**

```json
{
  "message": "Correctly API - AI-Powered Autocorrect",
  "version": "1.0.0",
  "status": "running"
}
```



### **POST /correct**

**Description:** Corrects the given text and returns results

**Request Body:**

```json
{
  "text": "Thiss is an exampel of a smple txt."
}
```

**Response:**

```json
{
  "corrected_text": "This is an example of a simple text.",
  "corrections_made": 3,
  "processing_time_ms": 45.23,
  "details": [
    {"original": "Thiss", "corrected": "This"},
    {"original": "exampel", "corrected": "example"},
    {"original": "smple", "corrected": "simple"}
  ]
}
```



### **GET /health**

**Description:** Health check endpoint
**Response:**

```json
{
  "status": "healthy",
  "dictionary_loaded": true
}
```



## 🧩 Technologies Used

* [FastAPI](https://fastapi.tiangolo.com/) – Web framework
* [SymSpellPy](https://github.com/mammothb/symspellpy) – Spell correction library
* [Pydantic](https://docs.pydantic.dev/) – Data validation
* [Uvicorn](https://www.uvicorn.org/) – ASGI server



## 🧪 Testing the API

You can test endpoints via:

* **Swagger UI:**
  👉 [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)
* **cURL:**

  ```bash
  curl -X POST "http://127.0.0.1:8000/correct" -H "Content-Type: application/json" -d "{\"text\": \"Thiss is an exampel\"}"
  ```



