# EaaS - API

This README describes how to generate and run the EaaS API using the [fastapi-code-generator library](https://github.com/koxudaxi/fastapi-code-generator) tool.

---

## Installation and Setup

### 1. Create a project folder

```bash
mkdir eaas_api
cd eaas_api
```

### 2. Create and activate a virtual environment (Linux)

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install required libraries

Install the code generator and dependencies:

```bash
pip install fastapi-code-generator
pip install "pydantic<2.0"
pip install "fastapi[standard]"
```

> `pydantic<2.0` is required due to compatibility with the generated code.

---

## Generate FastAPI Code from OpenAPI YAML

To generate the codebase from your OpenAPI file (e.g., `EaaS-openAPI.yaml`):

```bash
fastapi-codegen --input EaaS-openAPI.yaml --output ./app
```

This will create an `app/` folder with:
- `main.py` – FastAPI application entrypoint
- `models.py` – Pydantic models based on the OpenAPI schema

---

## Run the API server

```bash
uvicorn app.main:app --reload
```

Access the API docs:
- Swagger UI: [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)
- ReDoc: [http://127.0.0.1:8000/redoc](http://127.0.0.1:8000/redoc)

---

## Notes

The generated code does **not include route logic** — only models and route definitions.
