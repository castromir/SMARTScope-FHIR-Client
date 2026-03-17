# SMARTScope FHIR Client

A minimal, protocol-focused web application that implements the SMART on FHIR authorization flow using OAuth 2.0 Authorization Code with PKCE, and consumes clinical data from a FHIR server.

This project prioritizes integration correctness over UI complexity, demonstrating how a production-grade client interacts with EHR systems.

---

## Overview

This application:

- Authenticates via SMART on FHIR
- Implements OAuth 2.0 Authorization Code + PKCE
- Retrieves FHIR resources:
  - Patient
  - Observation
  - Encounter
- Parses FHIR Bundle responses
- Handles token lifecycle (including refresh)
- Applies filtering and error handling

---

## Architecture

Frontend (minimal UI)  
↓  
Backend (OAuth + API orchestration)  
↓  
FHIR Server (SMART-enabled EHR)

Layers implemented:

- Authentication layer (OAuth + PKCE)
- API client layer (FHIR requests)
- Data transformation layer (Bundle parsing)

---

## Tech Stack

- Backend: Node.js (Express) or Python (FastAPI)
- Frontend: Plain HTML or minimal React
- FHIR Server:
  - SMART sandbox (recommended)
  - or local HAPI FHIR (limited SMART support)

---

## SMART on FHIR Flow

### 1. App Registration

Register your app in a SMART-compatible environment.

You will receive:

- client_id
- authorization endpoint
- token endpoint
- FHIR base URL

Example redirect URI:
