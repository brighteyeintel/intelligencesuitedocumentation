# URL REST API Documentation

The `url` API endpoint allows developers to programmatically access the URL investigation tool, processing multiple URL queries in a single RESTful bulk POST request. 

## Endpoint

`POST /api/trinity/url`

## Authentication

You must provide a valid API key, tied to a valid registered user profile. Authentication methods supported:

1. **Request Body (Recommended):** An `Authentication` root key in the body.
2. **URL Parameter:** Appended via `?Authentication=secret`.

*(Session authentication is handled identically for internal client usage).*

## Request Structure

**Headers:**
- `Content-Type: application/json`

**Body (`application/json`):**
```json
{
  "Authentication": "YOUR_API_KEY",
  "querylist": [
    "example.com",
    "https://anotherexample.com"
  ]
}
```
*Missing protocol handlers like `http://` or `https://` are prepended as `https://` dynamically.*

## Credit Deduction
1 credit is consumed per unique valid URL supplied in the `querylist` array. If your associated user's credit balance is below the array length, a `402 Insufficient credits` is aborted safely before operations compile.

## Response Structure

For a complete mapping of specialized response objects, refer to the [URL Response Types](../types/url.md) documentation and [Shared Types](../types/shared.md).


Replies with HTTP Status `200` alongside a full TrinityResult housing URLSearchResults arrays respectively.

```json
{
  "searchMetadata": {
    "status": 200,
    "messageType": "results",
    "totalSearches": 2,
    "duration": "14.2s", // Usually takes longer as queries involve SSL, DNS, HTML Analysis
    "totalFound": 2,
    "route": "/api/trinity/url",
    "timestamp": "1712330000000"
  },
  "resultData": {
    "results": [
      {
         "domain": "example.com",
         "a_records": ["93.184.216.34"],
         "certificates": [],
         "wayback": {},
         "tranco_rank": 105,
         "html_analysis": {}
         // additional properties representing the lookup steps
      }
    ]
  },
  "scanId": 8391
}
```

## Error Responses
- **401 Unauthorized access**: Missing or invalid `Authentication`.
- **402 Insufficient credits**: Account credit balance too low relative to your `querylist.length`.
- **400 Bad Request**: The `querylist` is missing or 0 length.
