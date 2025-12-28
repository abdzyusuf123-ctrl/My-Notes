# API Design

An **API** is a way for microservices to communicate with each other by sending data back and forth.

---

## What an API Defines

1. The types of communication  
2. The data that must be sent  
3. The data that will be returned  
4. The status codes that can occur  

---

## Types of Communication

There are **four main HTTP methods** used for communication between microservices.

---

### GET Request

Used **only to fetch data** and never to update data.

**Properties (interview gold):**
- Safe  
- Can be retried  
- Can be cached  
- No side effects  

---

### POST Request

Used to **create a new record**.

**Properties:**
- Not safe — creates or triggers something  
- Not retriable by default — retrying may create duplicates  
- Not cacheable — responses are usually not reused  
- Has side effects  

POST requests become safer when **idempotency** is implemented  
(e.g., a unique ID for each unique request).

---

### PUT / PATCH Requests

Used to **update existing records**:
- `PUT` → replace the entire record  
- `PATCH` → partially update a record  

**Properties:**
- Not safe — modifies existing state  
- Conditionally retriable  
  - `PATCH` → often unsafe to retry blindly  
  - `PUT` → usually idempotent  
- Not cacheable — responses depend on current state  
- Has side effects — updates data  

---

### DELETE Request

Used to **delete a record**.

**Properties:**
- Not safe — removes or deactivates a resource  
- Usually idempotent — deleting the same resource twice gives the same result  
- Not cacheable  
- Has side effects  

---

## Request & Response Data

- The data that must be sent and returned is usually dictated by the endpoint  
- Most APIs use **JSON** as the data format  

---

## Status Codes

Status codes indicate the result of an API request.

---

### Success Responses (2xx)

| Status Code | Name       | When to Use                                  | Example                    |
|------------|------------|----------------------------------------------|----------------------------|
| **200**    | OK         | Successful read or update                    | `GET /payments/123 → 200`  |
| **201**    | Created    | Resource successfully created                | `POST /payments → 201`     |
| **204**    | No Content | Success with no response body (often DELETE) | `DELETE /payments/123`     |

---

### Client Errors (4xx)

| Status Code | Name         | When to Use                                              | Example / Notes                           |
|------------|--------------|----------------------------------------------------------|-------------------------------------------|
| **400**    | Bad Request  | Invalid input, missing fields, validation failed         | `{ "error": "amount must be positive" }` |
| **401**    | Unauthorized | Missing or invalid authentication token                  | “Who are you?” ❌                         |
| **403**    | Forbidden    | Authenticated but not allowed                            | “I know who you are — you can’t do this.” |
| **404**    | Not Found    | Resource doesn’t exist or is hidden                      | `GET /payments/x → 404`                  |
| **409**    | Conflict    | Duplicate request or state conflict                      | Duplicate payment                         |

---

### Server Errors (5xx)

| Status Code | Name                  | When to Use                               | Notes                                         |
|------------|-----------------------|-------------------------------------------|-----------------------------------------------|
| **500**    | Internal Server Error | Unexpected failure, bug, dependency crash | Log internally, never expose internals         |
| **503**    | Service Unavailable   | Temporary outage or overload              | Signals clients to retry later                |

---

## API Flow

```
Client sends request → Server validates request → Business rules are applied → Data is read/updated (CRUD) → Server returns response → Client handles result

```
