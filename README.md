# SMARTScope FHIR Client

A minimal, protocol-focused web application that implements the SMART on FHIR authorization flow using OAuth 2.0 Authorization Code with PKCE, and consumes clinical data from a FHIR server.

This project prioritizes integration correctness over UI complexity, demonstrating how a production-grade client interacts with EHR systems.

---

## Core Objectives

- Implement full SMART on FHIR authentication flow
- Use OAuth 2.0 Authorization Code + PKCE securely
- Retrieve and process FHIR resources:
  - Patient
  - Observation
  - Encounter
- Parse and normalize FHIR Bundle responses
- Handle token lifecycle (including refresh)
- Apply filtering and error handling strategies

---

## Architecture Overview

Frontend (minimal UI)  
↓  
Backend (OAuth orchestration + FHIR client)  
↓  
FHIR Server (SMART-enabled EHR sandbox or HAPI FHIR)

This project explicitly separates:

- Authentication layer (OAuth + PKCE)
- API client layer (FHIR requests)
- Data transformation layer (Bundle parsing)

---

## Tech Stack (Suggested)

- Backend: Node.js (Express) or Python (FastAPI)
- Frontend: Plain HTML or minimal React
- FHIR Server:
  - SMART sandbox (recommended)
  - or local HAPI FHIR (limited SMART support)

---

## SMART on FHIR Flow Implementation

### 1. App Registration

Register the application in a SMART-compatible environment.

You will receive:

- client_id
- Authorization endpoint
- Token endpoint
- FHIR base URL

Define a redirect URI, e.g.:
