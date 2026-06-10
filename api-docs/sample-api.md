# TaskFlow API Reference

Base URL: https://api.taskflow.io/v1

Authentication: Bearer token in Authorization header

---


# Request Parameters

| Parameter   | Type     | Required  | Description                                 |
|-------------|----------|----------|----------------------------------------------|
| title       | string   | Yes      | Task title (max 255 characters)              |
| due_date    | string   | No       | ISO 8601 date string (YYYY-MM-DD)            |
| priority    | string   | No       | Low, medium, or high. Default: medium        |
| assignee_id | integer  | No       | User ID of the assignee                      |


---
  
### Example request 
```bash
curl -X POST https://api.taskflow.io/v1/tasks \
  -H 'Authorization: Bearer YOUR_TOKEN' \
  -H 'Content-Type: application/json' \
  -d '{
    "title": "Write onboarding guide",
    "due_date": "2025-06-30",
    "priority": "high",
    "assignee_id": 42
  }'
```
  
### Example response (201 Created) 
```json
{
  "id": 1024,
  "title": "Write onboarding guide",
  "due_date": "2025-06-30",
  "priority": "high",
  "status": "open",
  "assignee_id": 42,
  "created_at": "2025-05-31T10:22:00Z"
}
```
#### Error Responses

| Status Code | Description                                 |
|-------------|---------------------------------------------|
| 400         | A required field is missing or malformed    |
| 401         | Token is missing or expired                 |
| 422         | Due date is in the past                     |










