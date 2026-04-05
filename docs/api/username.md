# Username REST API Documentation

The `username` API endpoint offers developers programmatic interfacing capacities against OSINT directory lookups finding registrations spanning numerous distinct external networks and hubs mapping standard string usernames over REST bulk queries.

## Endpoint

`POST /api/trinity/username`

## Authentication

Authentication is required and validated. Expose the assigned developer keys respectively.

1. **Request Body (Default):** Include key mappings internal to payload. `"Authentication": "xyz"`.
2. **URL Hooking:** Parse explicitly over query parameters via `?Authentication=xyz`.

## Request Structure

**Headers:**
- `Content-Type: application/json`

**Body (`application/json`):**
```json
{
  "Authentication": "YOUR_API_KEY",
  "querylist": [
    "user123",
    "developername"
  ]
}
```

## Credit Deduction
Functions normally resolve deductions aligned to `querylist` values against the connected identity balances. Missing prerequisites return a `402` runtime error.

## Response Structure

For a complete mapping of specialized response objects, refer to the [Username Response Types](../types/username.md) documentation and [Shared Types](../types/shared.md).


Success resolves correctly with HTTP Status `200` outputting the `UsernameSearchResults` object enclosed implicitly within native `TrinityResult` metadata representations.

```json
{
  "searchMetadata": {
    "status": 200,
    "messageType": "results",
    "totalSearches": 2,
    "duration": "10.45s", // OSINT queries often carry duration lags
    "totalFound": 2,
    "route": "/api/trinity/username",
    "timestamp": "1712330000000"
  },
  "resultData": {
    "results": [
      {
         // Comprehensive directory listings spanning social hub links.
      }
    ]
  },
  "scanId": 6732
}
```

## Error Responses
- **401 Unauthorized access**: Missing authentication values.
- **402 Insufficient credits**: Exceeded credit quota.
- **400 Bad Request**: Empty or improperly structured list object.
