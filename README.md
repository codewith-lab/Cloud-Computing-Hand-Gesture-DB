# Overview

This database schema supports storing user text inputs and corresponding sentiment analysis results. 

---

## `requests` Table

Stores user text input requests submitted for sentiment analysis.

| Column Name | Type | Description |
|--------------|------|-------------|
| **id** | `VARCHAR(36)` | Primary key — unique identifier for each request |
| **input_text** | `TEXT` | The user’s text input to analyze |
| **user_id** | `VARCHAR(36)` | Identifier for the user who made the request |
| **created_at** | `TIMESTAMP` | Timestamp when the request was created |

---

## `sentiments` Table

Stores the sentiment analysis results for each request.

| Column Name | Type | Description |
|--------------|------|-------------|
| **id** | `VARCHAR(36)` | Primary key — unique identifier for each analysis result |
| **request_id** | `VARCHAR(36)` | Foreign key referencing `requests.id` |
| **sentiment** | `VARCHAR(20)` | Sentiment classification (e.g., `positive`, `neutral`, `negative`) |
| **confidence** | `DECIMAL(3,2)` | Confidence score ranging from `0.00` to `1.00` |
| **analyzed_at** | `TIMESTAMP` | Timestamp when the sentiment analysis was performed |

---
