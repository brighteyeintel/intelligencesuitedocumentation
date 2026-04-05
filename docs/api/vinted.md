# Vinted REST API Documentation

The `vinted` API endpoint offers specialized program functionality integrating to extract product queries, or merchant strings seamlessly via the RESTful API architectures resolving lists natively.

## Endpoint

`POST /api/trinity/vinted`

## Authentication

All routes secure themselves matching authentication hooks verified natively across the database. Provide authentication context to progress parsing logic flows.

1. **Request Body:** Specify an `Authentication` root key within the general JSON structure passing a string assignment matching keys securely.
2. **URL Header Values:** Target explicit overrides routing parameter keys natively via `?Authentication=secure_value`.

## Request Structure

**Headers:**
- `Content-Type: application/json`

**Body (`application/json`):**
```json
{
  "Authentication": "YOUR_API_KEY",
  "querylist": [
    "merchant123",
    "search query terms"
  ]
}
```

## Credit Deduction
Credit costs inherently deduct values explicitly mapped against lengths natively evaluating string parameters submitted inside mapping structures preventing system overuse triggering standard error flag `402 Insufficient credits` safely before parsing overhead initiates execution values.

## Response Structure

For a complete mapping of specialized response objects, refer to the [Vinted Response Types](../types/vinted.md) documentation and [Shared Types](../types/shared.md).


Execution properly validates mapped inputs generating a typical TrinityResult bounding arrays referencing native VintedSearchResults objects correctly. Target `200` output standard codes correctly.

```json
{
  "searchMetadata": {
    "status": 200,
    "messageType": "results",
    "totalSearches": 2,
    "duration": "3.55s",
    "totalFound": 2,
    "route": "/api/trinity/vinted",
    "timestamp": "1712330000000"
  },
  "resultData": {
    "results": [
      {
         // Market products, matching results, or native merchant profiles retrieved.
      }
    ]
  },
  "scanId": 2981
}
```

## Error Responses
- **401 Unauthorized access**: Passed missing invalid explicit permission keys.
- **402 Insufficient credits**: Valid thresholds missed over constraints.
- **400 Bad Request**: JSON representation values incorrectly managed dynamically.
