# Greek-Site Southbound Plugin API

This repository contains the Southbound Plugin API for the Greek-Site infrastructure, built with FastAPI and containerized with Docker.

## Features

- **Application Management**
  - Application Onboarding
  - Create Application Instance
  - Stop Application Instance
- **Monitoring**
  - Get Instance State

## Prerequisites

- Python 3.10 or higher
- Docker and Docker Compose
- Git

## Development Setup

### 1. Clone the Repository

```bash
git clone https://github.com/fogusinnovations/envelope_eaas_api.git
cd envelope_eaas_api
```

### 2. Create and Activate Virtual Environment

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

## Running the API

### Using Docker (Recommended)

The project includes Docker configuration for both the API and Nginx reverse proxy:

```bash
docker compose up --build
```

This will:
- Build and start the API container
- Set up Nginx as a reverse proxy
- Make the API available at http://localhost/api/

### Local Development

For local development without Docker:

```bash
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```

## API Documentation

Once running, access the API documentation at:
- Swagger UI: http://localhost/docs
- ReDoc: http://localhost/redoc

## Code Generation

The API generated using [fastapi-code-generator library](https://github.com/koxudaxi/fastapi-code-generator). To regenerate the code:

```bash
fastapi-codegen --input EaaS-openAPI.yaml --output app --output-model-type pydantic_v2.BaseModel
```

