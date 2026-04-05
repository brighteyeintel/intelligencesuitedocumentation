# VehicleReg REST API Documentation

The `vehiclereg` API dynamically interfaces natively resolving vehicle registration numbers into specific hardware details regarding the motor registration profiles over bulk standardized request structures. 

## Endpoint

`POST /api/trinity/vehiclereg`

## Authentication

Authenticate payloads explicitly passing assigned keys matching internal databases representing distinct user access rights.

1. **Request Body:** Encrypt explicitly via an `Authentication` json key binding natively inside parsing objects.
2. **URL Parameters:** Assign query sequences explicitly `?Authentication=secret_key`.

## Request Structure

**Headers:**
- `Content-Type: application/json`

**Body (`application/json`):**
```json
{
  "Authentication": "YOUR_API_KEY",
  "querylist": [
    "AB12CDE",
    "123XYZ"
  ]
}
```

## Credit Deduction
A `402 Insufficient credits` flag is immediately thrown assuming credit thresholds evaluated drop underneath computational boundaries representing lengths derived implicitly from the string items submitted over the requests.

## Response Structure

Resolves universally to a standardized wrapping layer matching HTTP Status `200` including payload metadata bounding `VehicleRegSearchResults`.

```json
{
  "searchMetadata": {
    "status": 200,
    "messageType": "results",
    "totalSearches": 2,
    "duration": "1.52s",
    "totalFound": 2,
    "route": "/api/trinity/vehiclereg",
    "timestamp": "1712330000000"
  },
  "resultData": {
    "results": [
      {
         // Car make, model layout, registration date mappings parsed implicitly.
      }
    ]
  },
  "scanId": 8223
}
```

## Error Responses
- **401 Unauthorized access**: The passed authentication parameter lacked permission arrays.
- **402 Insufficient credits**: User balance bounds limit queries execution.
- **400 Bad Request**: General invalid payload format variables triggered failures.
