# Email REST API Documentation

The `email` API endpoint allows developers to programmatically access the Email lookup tool, processing multiple queries in a single RESTful bulk POST request.

## Endpoint

`POST /api/trinity/email`

## Authentication

All internal Trinity APIs require authentication. You must provide a valid API key, which is associated with your user account. There are two ways to authenticate:

1. **Request Body (Recommended):** Include an `Authentication` key in the JSON body.
2. **URL Parameter:** Append `?Authentication=secret` to the endpoint.

*(Session authentication is also supported if invoked dynamically from the frontend).*

## Request Structure

**Headers:**
- `Content-Type: application/json`

**Body (`application/json`):**
```json
{
  "Authentication": "YOUR_API_KEY",
  "querylist": [
    "target1@example.com",
    "target2@example.com"
  ]
}
```
*Note: Duplicate strings in `querylist` are automatically removed before execution.*

## Credit Deduction
A balance check is performed upfront. The tool deducts 1 credit per valid unique query submitted in the `querylist`. If your balance is lower than the required amount, you will receive a `402` status.

## Response Structure

For a complete mapping of specialized response objects, refer to the [Email Response Types](../types/email.md) documentation and [Shared Types](../types/shared.md).


The endpoint normally returns HTTP Status `200` with a generic TrinityResult wrapper containing the EmailSearchResults object.

```json
{
  "searchMetadata": {
    "status": 200,
    "messageType": "results",
    "totalSearches": 2,
    "duration": "1.23s",
    "totalFound": 2,
    "route": "/api/trinity/email",
    "timestamp": "1712330000000"
  },
  "resultData": {
    "results": [
      {
        // Email specific lookup details (e.g. breach info, provider details)
      }
    ]
  },
  "scanId": 984
}
```

## Error Responses
- **401 Unauthorized access**: Missing or invalid `Authentication`.
- **402 Insufficient credits**: Account credit balance too low.
- **400 Bad Request**: The `querylist` is missing or empty.
