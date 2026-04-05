# Company REST API Documentation

The `company` API endpoint allows developers to programmatically interface with business information registry lookups. It processes multiple business registrations/terms in a single RESTful bulk POST request.

## Endpoint

`POST /api/trinity/company`

## Authentication

You must establish authorization. Provide a valid API key tied to your identity through one of the following methods:

1. **Request Body (Recommended):** Add an `Authentication` explicit key resolving to your API key.
2. **URL Parameter:** Add `?Authentication=YOUR_KEY`

## Request Structure

**Headers:**
- `Content-Type: application/json`

**Body (`application/json`):**
```json
{
  "Authentication": "YOUR_API_KEY",
  "querylist": [
    "01234567",
    "Example Limited"
  ]
}
```
*Note: Duplicate arguments natively get removed.*

## Credit Deduction
Generally consumes credits relative to the size parameters queried in the `querylist`. Ensure your connected user identity yields adequate funds. Results in `402` logic branches on negative availability.

## Response Structure

Responds effectively with HTTP `200` holding a TrinityResult context wrapping CompanySearchResults arrays.

```json
{
  "searchMetadata": {
    "status": 200,
    "messageType": "results",
    "totalSearches": 2,
    "duration": "0.68s",
    "totalFound": 2,
    "route": "/api/trinity/company",
    "timestamp": "1712330000000"
  },
  "resultData": {
    "results": [
      {
         // Detailed firm registration, financials, standing context
      }
    ]
  },
  "scanId": 7943
}
```

## Error Responses
- **401 Unauthorized access**: API verification failed.
- **402 Insufficient credits**: Account credit amount invalid vs workload queried.
- **400 Bad Request**: Invalid body format bindings.
