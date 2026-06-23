# System Architecture

## Overview

The AI Job Market Intelligence Platform follows a **Modular Monolithic Architecture**, where all core components exist within a single application while remaining logically separated into independent modules.

This architecture provides a balance between simplicity, maintainability, and scalability. Each module has a well-defined responsibility, making future migration to a microservices architecture possible if required.

---

# Architecture Overview

                    User
                      │
                      ▼
              React Frontend
                      │
                REST API (HTTP)
                      │
                      ▼
              FastAPI Backend
                      │
    ┌─────────────────┼─────────────────┐
    │                 │                 │
    ▼                 ▼                 ▼
 Analytics      Job Management      AI Services
    │                 │                 │
    └─────────────────┼─────────────────┘
                      │
              Business Services
                      │
              Repository Layer
                      │
                SQLAlchemy ORM
                      │
                 PostgreSQL
                      ▲
                      │
                ETL Pipeline
                      ▲
                      │
            Web Scraper Engine
                      ▲
                      │
               Job Websites

---

# Architectural Style

The project adopts a **Layered Modular Monolith** architecture.

Each layer is responsible for a single concern.

Presentation Layer

- React Dashboard
- Data Visualization
- Search Interface

Application Layer

- REST API
- Request Validation
- Authentication (Future)

Business Layer

- Analytics
- Skill Extraction
- Salary Analysis
- Recommendation Logic

Data Layer

- SQLAlchemy ORM
- PostgreSQL Database

Infrastructure Layer

- Web Scraper
- ETL Pipeline
- Logging
- Configuration
- Scheduled Jobs

---

# Component Description

## Frontend

Responsibilities

- Display dashboard
- Search jobs
- Visualize analytics
- Communicate with backend APIs

Technology

- React
- TypeScript

---

## Backend

Responsibilities

- Receive API requests
- Execute business logic
- Query database
- Return JSON responses

Technology

- FastAPI

---

## Database

Responsibilities

- Store structured job data
- Store companies
- Store skills
- Store analytics

Technology

- PostgreSQL

---

## Web Scraper

Responsibilities

- Collect job postings
- Parse HTML
- Validate data
- Send raw data to ETL

Technology

- Playwright
- BeautifulSoup

---

## ETL Pipeline

Responsibilities

Extract

↓

Transform

↓

Load

Tasks

- Clean data
- Remove duplicates
- Normalize skills
- Standardize salary
- Validate locations

---

## Analytics Engine

Responsibilities

Generate

- Skill demand
- Salary statistics
- Hiring trends
- Company analytics
- Location insights

---

## AI Engine

Responsibilities

Future AI features

- Resume Matching
- Skill Extraction
- Salary Prediction
- Career Recommendation
- Demand Forecasting

---

# Request Flow

Example

User searches

"Python Developer"

↓

Frontend

↓

GET /jobs?skill=Python

↓

FastAPI

↓

Service Layer

↓

Repository Layer

↓

PostgreSQL

↓

JSON Response

↓

Frontend

↓

Dashboard Update

---

# Data Flow

Job Websites

↓

Scraper

↓

Raw Data

↓

ETL Pipeline

↓

Database

↓

Analytics

↓

REST API

↓

Frontend

↓

User

---

# Module Communication

Frontend
        │
REST API
        │
Backend
        │
Service Layer
        │
Repository Layer
        │
Database

---

# Scalability

The architecture is designed to support:

- Additional job sources
- New AI models
- More dashboard modules
- Background workers
- Distributed deployment

without major architectural changes.

---

# Technology Stack

Frontend

- React
- TypeScript

Backend

- FastAPI

Database

- PostgreSQL
- SQLAlchemy

AI

- Scikit-learn
- spaCy
- Sentence Transformers

Scraping

- Playwright
- BeautifulSoup

Deployment

- Docker

---

# Architectural Principles

The project follows the following software engineering principles:

- Separation of Concerns
- Modular Design
- Layered Architecture
- Single Responsibility Principle
- Reusability
- Scalability
- Maintainability