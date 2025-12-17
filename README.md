🏥 Patient Management System API (FastAPI)

A simple Patient Management REST API built using FastAPI and Pydantic v2.
The project demonstrates CRUD operations, request validation, computed fields, and basic data persistence using a JSON file.

⚠️ Note: This project is for learning and practice purposes. It is not production-ready.

🚀 Features

Create, Read, Update, Delete (CRUD) patient records

Automatic BMI calculation

Health verdict based on BMI

Sort patients by height, weight, or BMI

Strong request validation using Pydantic

Lightweight JSON-based storage

🛠 Tech Stack

Backend Framework: FastAPI

Validation: Pydantic v2

Server: Uvicorn

Storage: JSON file (patients.json)

Language: Python 3.10+

📁 Project Structure
.
├── main.py
├── patients.json
├── requirements.txt
└── README.md

📦 Requirements

Create a virtual environment (recommended):

python -m venv venv
source venv/bin/activate   # Linux / macOS

venv\Scripts\activate      # Windows


Install dependencies:

pip install -r requirements.txt

requirements.txt
fastapi>=0.110.0
pydantic>=2.0
uvicorn>=0.23.0

▶️ Running the Application

Start the FastAPI server:

uvicorn main:app --reload


API will be available at:

http://127.0.0.1:8000


Interactive API Docs:

Swagger UI → http://127.0.0.1:8000/docs

Redoc → http://127.0.0.1:8000/redoc

📌 API Endpoints
General
Method	Endpoint	Description
GET	/	API health check
GET	/about	API description
Patient Operations
Method	Endpoint	Description
GET	/view	View all patients
GET	/patient/{id}	View patient by ID
POST	/create	Create new patient
PUT	/edit/{id}	Update patient
DELETE	/delete/{id}	Delete patient
Sorting
Method	Endpoint
GET	/sort?sort_by=bmi&order=asc

Valid sort_by values:

height

weight

bmi

🧮 Computed Fields
BMI Calculation
BMI = weight / (height²)

Health Verdict

< 18.5 → Underweight

18.5 – 24.9 → Normal

25 – 29.9 → Overweight

≥ 30 → Obese

These fields are auto-generated and cannot be manually edited.

⚠️ Limitations (Read This Honestly)

This project:

❌ Does NOT use a real database

❌ Has no authentication or authorization

❌ Is not safe for concurrent users

❌ Is not scalable

This is practice-level backend work, not an industry-grade system.

🎯 Learning Outcomes

FastAPI routing & validation

Pydantic v2 (Annotated, computed_field)

CRUD API design

Error handling with HTTP exceptions

Data persistence using JSON

📌 Future Improvements

Replace JSON with PostgreSQL / MongoDB

Add JWT authentication

Add pagination & filtering

Add unit tests

Dockerize the application
