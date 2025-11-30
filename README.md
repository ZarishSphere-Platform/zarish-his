# Zarish-HIS (Health Information System Module)

Clinical data management module for ZarishSphere Platform, providing comprehensive Electronic Health Record (EHR) capabilities.

## Features

- **Patient Management**: Registration, demographics, and history.
- **Encounter Tracking**: Inpatient and outpatient visits.
- **Clinical Data**: Vitals, Notes, Medications, Labs, and Allergies.
- **Billing & Insurance**: Invoicing, payments, and claims management.
- **FHIR Compliance**: Data models aligned with HL7 FHIR standards.

## Architecture

The system is built using a clean architecture pattern:

- **API Layer**: RESTful endpoints using Gin framework.
- **Service Layer**: Business logic and orchestration.
- **Repository Layer**: Data access using GORM.
- **Models**: FHIR-compliant data structures.

## API Endpoints

### Patients

- `POST /api/v1/patients` - Create patient
- `GET /api/v1/patients/:id` - Get patient by ID
- `GET /api/v1/patients` - List patients (paginated)

### Encounters

- `POST /api/v1/encounters` - Create encounter
- `GET /api/v1/encounters/patient/:id` - Get encounters for a patient

### Billing

- `POST /api/v1/billing/invoices` - Generate invoice
- `POST /api/v1/billing/payments` - Record payment
- `POST /api/v1/billing/claims` - Submit insurance claim

## Running Locally

### Prerequisites

- Go 1.23+
- PostgreSQL 15+
- Docker (optional)

### Steps

1. **Configure Database**: Ensure PostgreSQL is running and update `config.yaml` or environment variables.
2. **Run Server**:
   ```bash
   go run cmd/server/main.go
   ```
   Server runs on port **8083**.

## Docker Support

The service is containerized. Build and run using Docker Compose:

```bash
docker-compose up --build zarish-his
```

## Technology Stack

- **Language**: Go 1.23
- **Framework**: Gin
- **ORM**: GORM
- **Database**: PostgreSQL
- **Documentation**: Swagger/OpenAPI (planned)
