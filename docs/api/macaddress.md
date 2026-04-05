# Macaddress REST API Documentation

The `macaddress` API endpoint provides developers with an interface to programmatically derive hardware vendor assignments associated with specific MAC addresses. The architecture supports bulk POST processing to maximize throughput.

## Endpoint

`POST /api/trinity/macaddress`

## Authentication

All internal Trinity APIs require access clearance via an API Key.

1. **Request Body (Recommended):** An `Authentication` JSON root level key mapping to your user API key.
2. **URL Parameter:** Explicit argument string passed via `?Authentication=KEY_HERE`.

## Request Structure

**Headers:**
- `Content-Type: application/json`

**Body (`application/json`):**
```json
{
  "Authentication": "YOUR_API_KEY",
  "querylist": [
    "00:1A:2B:3C:4D:5E",
    "00-1B-44-11-3A-B7"
  ]
}
```

## Credit Deduction
A sequential cost of 1 credit is typically deducted per valid MAC Address pushed through the `querylist` constraint. `402 Insufficient credits` blocks operations upfront if boundaries are exceeded organically.

## Response Structure

For a complete mapping of specialized response objects, refer to the [Mac Address Response Types](../types/bssid.md) documentation and [Shared Types](../types/shared.md).


The endpoint signals an HTTP `200` completion binding results strictly within the TrinityResult architectural standard payload format.

```json
{
  "searchMetadata": {
    "status": 200,
    "messageType": "results",
    "totalSearches": 2,
    "duration": "0.19s",
    "totalFound": 2,
    "route": "/api/trinity/macaddress",
    "timestamp": "1712330000000"
  },
  "resultData": {
    "results": [
      {
         // Hardware vendor name, assignment block logic, bounds.
      }
    ]
  },
  "scanId": 1412
}
```

## Error Responses
- **401 Unauthorized access**: Missing or expired Authentication context.
- **402 Insufficient credits**: User quota low.
- **400 Bad Request**: JSON array parameters formatted unexpectedly.
