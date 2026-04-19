# Real-Time Notification Service (Backend Task)

## Overview

This task is designed to evaluate your skills as a **mid-level Python backend developer**. You will build a simple real-time notification system using:

* Python (preferably FastAPI)
* WebSockets
* Docker

The goal is to assess your ability to design, structure, and implement a small but realistic backend system.

---

## Features to Implement

### 1. WebSocket Support

* Endpoint: `/ws/{user_id}`
* Users connect via WebSocket using their `user_id`
* Maintain active connections
* When a notification is created, send it instantly to the connected user

---

### 2. REST API

#### ➤ Create Notification

```
POST /notifications
```

**Request Body:**

```json
{
  "user_id": "123",
  "message": "Hello from system"
}
```

**Behavior:**

* Store notification in database
* If user is connected → push via WebSocket

---

#### ➤ Get Notifications

```
GET /notifications/{user_id}
```

**Behavior:**

* Return all stored notifications for the user

---

## Data Storage

Use **SQLite** for simplicity. If you are familiar with any other databases, feel free to use them

### Notification Model

* `id` (int, primary key)
* `user_id` (string)
* `message` (string)
* `created_at` (timestamp)

---

## Docker Requirements

Your application must be runnable via Docker.

### Required Files:

* `Dockerfile`
* `docker-compose.yml`

### Run Command:

```
docker-compose up --build
```

---

## Functional Expectations

* Handle multiple WebSocket connections
* Cleanly manage connection lifecycle (connect/disconnect)
* Remove stale/dead connections
* Basic error handling for:

  * Invalid inputs
  * WebSocket disconnects
  * Database operations

---

## Evaluation Criteria

### Must Have

* Working REST + WebSocket implementation
* Proper async handling
* Dockerized setup runs successfully
* Clean, readable code

---

### Strong Candidate Signals

* Good separation of concerns
* Service layer abstraction
* Thoughtful error handling
* Sensible project organization (left intentionally open-ended)

---

### Bonus Points

* DDD-inspired architecture
* Unit tests
* Logging
* Environment-based configuration
* Type hints

---

## Time Expectation

This task is designed to be completed in **6–7 hours**.

---

## Deliverables

* Git repository
* Fully working code
* `README.md` with:

  * Setup instructions
  * API usage
  * Design decisions

---

## ⚠️ Disclaimer

* Submissions that are **fully AI-generated without clear understanding** will not be accepted.
* Be prepared to **explain your design decisions and code** during follow-up discussions.
* The way you **structure your project is part of the evaluation**, so no predefined structure is provided intentionally.

---

## Notes

* Focus on **clean design over over-engineering**
* Keep it simple, but thoughtful
* Write code as if it will be maintained by a team

---

Best of Luck :)
