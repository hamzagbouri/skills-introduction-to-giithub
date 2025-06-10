# Quote Generator API Documentation

## Base URL
```
/api/v1
```

## Endpoints

### Get All Quotes
```http
GET /quotes
```

Query Parameters:
- `category` (optional): Filter quotes by category

Response:
```json
[
    {
        "id": "123",
        "content": "Quote text",
        "author": "Author name",
        "category": "Category name",
        "created_at": "2024-03-21 10:00:00"
    }
]
```

### Get Random Quote
```http
GET /quotes/random
```

Query Parameters:
- `category` (optional): Get random quote from specific category

Response:
```json
{
    "id": "123",
    "content": "Quote text",
    "author": "Author name",
    "category": "Category name",
    "created_at": "2024-03-21 10:00:00"
}
```

### Get Quote by ID
```http
GET /quotes/{id}
```

Response:
```json
{
    "id": "123",
    "content": "Quote text",
    "author": "Author name",
    "category": "Category name",
    "created_at": "2024-03-21 10:00:00"
}
```

### Create New Quote
```http
POST /quotes
```

Request Body:
```json
{
    "content": "Quote text",
    "author": "Author name",
    "category": "Category name"
}
```

Response (201 Created):
```json
{
    "id": "123",
    "content": "Quote text",
    "author": "Author name",
    "category": "Category name",
    "created_at": "2024-03-21 10:00:00"
}
```

### Update Quote
```http
PUT /quotes/{id}
```

Request Body:
```json
{
    "content": "Updated quote text",
    "author": "Updated author name",
    "category": "Updated category"
}
```

Response:
```json
{
    "id": "123",
    "content": "Updated quote text",
    "author": "Updated author name",
    "category": "Updated category",
    "created_at": "2024-03-21 10:00:00"
}
```

### Delete Quote
```http
DELETE /quotes/{id}
```

Response:
```json
{
    "id": "123",
    "content": "Quote text",
    "author": "Author name",
    "category": "Category name",
    "created_at": "2024-03-21 10:00:00"
}
```

## Error Responses

All endpoints may return the following error responses:

### 404 Not Found
```json
{
    "error": "Quote not found"
}
```

### 400 Bad Request
```json
{
    "error": "Invalid request data"
}
```

## Notes
- All timestamps are in ISO 8601 format
- Category filtering is case-sensitive
- The API uses in-memory storage, so data will be reset when the server restarts 
