# IP REST API Documentation

The `ip` API endpoint allows developers to programmatically access the IP lookup service, processing multiple IP queries in a single RESTful bulk POST request.

## Endpoint

`POST /api/trinity/ip`

## Authentication

All internal Trinity APIs require authentication. You must provide a valid API key, which is associated with your user account. There are two ways to authenticate:

1. **Request Body (Recommended):** Include an `Authentication` key in the JSON body.
2. **URL Parameter:** Append `?Authentication=secret` to the endpoint.

## Request Structure

**Headers:**
- `Content-Type: application/json`

**Body (`application/json`):**
```json
{
  "Authentication": "YOUR_API_KEY",
  "querylist": [
    "8.8.8.8",
    "1.1.1.1"
  ]
}
```
*Note: Duplicate queries in `querylist` are automatically removed before execution.*

## Credit Deduction
A balance check is performed upfront securely checking the required amount. Wait, IP endpoint currently deducts a flat 1 credit per POST query (not per `querylist` item directly). Ensure you bundle arrays correctly. A `402` status is returned on insufficient balance.

## Response Structure

The endpoint normally returns HTTP Status `200`. The response is a standard [`TrinityResult`](../types/shared.md#trinityresult) wrapping an [`IPSearchResults`](../types/ip.md#ipsearchresults) object.

For a complete reference of the available serialized types, see the [IP Response Types](../types/ip.md).

```json
{
  "searchMetadata": {
    "status": 200,
    "messageType": "results",
    "totalSearches": 2,
    "duration": "0.85s",
    "totalFound": 2,
    "route": "/api/trinity/ip",
    "timestamp": "1712330000000"
  },
  "resultData": {
    "results": [
      {
         // Detailed IP intelligence (ThreatFox, DroneBL, etc.)
      }
    ]
  },
  "scanId": 4512
}
```

## Error Responses
- **401 Unauthorized access**: Missing or invalid authentication API key.
- **402 Insufficient credits**: Credit balance must be >= 1.
