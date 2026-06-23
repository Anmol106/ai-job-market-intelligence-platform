# API Design

## Overview

The AI Job Market Intelligence Platform exposes a RESTful API built using FastAPI.

The API serves as the communication layer between the frontend dashboard, backend services, and AI modules.

All responses are returned in JSON format.

Base URL

/api/v1

---

# API Modules

The API is divided into logical modules.

- Jobs
- Companies
- Skills
- Analytics
- Predictions
- Health

---

# Health API

## GET /health

Purpose

Check whether the backend service is running.

Response

Status: 200 OK

{
    "status": "healthy",
    "service": "AI Job Market Intelligence Platform"
}

---

# Jobs API

## GET /jobs

Description

Returns a paginated list of jobs.

Query Parameters

- keyword
- location
- company
- experience
- salary
- employment_type
- remote
- page
- limit

Example

GET /jobs?keyword=Python&page=1

---

## GET /jobs/{id}

Description

Returns complete information for a single job.

---

## POST /jobs

Description

Insert a new job into the database.

(Currently used by scraper.)

---

## PUT /jobs/{id}

Description

Update an existing job.

---

## DELETE /jobs/{id}

Description

Remove a job.

---

# Companies API

## GET /companies

Returns all companies.

---

## GET /companies/{id}

Returns company information.

---

## GET /companies/{id}/jobs

Returns jobs posted by a company.

---

# Skills API

## GET /skills

Returns all extracted skills.

---

## GET /skills/trending

Returns currently trending skills.

---

## GET /skills/{name}

Returns statistics for a skill.

Example

Python

Average Salary

Number of Jobs

Top Companies

Demand Trend

---

# Analytics API

## GET /analytics/overview

Returns

- Total Jobs
- Companies
- Skills
- Average Salary

---

## GET /analytics/salary

Returns salary statistics.

---

## GET /analytics/trends

Returns hiring trends.

---

## GET /analytics/locations

Returns location analytics.

---

## GET /analytics/experience

Returns experience distribution.

---

## GET /analytics/companies

Returns company analytics.

---

# AI APIs

## POST /predict/salary

Input

{
    "skills":[
        "Python",
        "FastAPI",
        "SQL"
    ],
    "experience":2,
    "location":"Delhi"
}

Output

{
    "predicted_salary":1200000
}

---

## POST /predict/skill-gap

Input

Resume

↓

Output

Missing Skills

Recommended Learning Path

---

## POST /recommend/career

Returns AI-generated career recommendations.

---

# Response Format

Success

{
    "success": true,
    "data": { }
}

Error

{
    "success": false,
    "message": "Job not found"
}

---

# Status Codes

200 OK

201 Created

400 Bad Request

404 Not Found

500 Internal Server Error

---

# Future APIs

Authentication

Bookmarks

User Dashboard

Resume Upload

Notifications

Learning Roadmap

Admin Dashboard