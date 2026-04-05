# Phone REST API Documentation

The `phone` API endpoint exposes a uniform programmatic handler for parsing and inspecting metadata bound to E.164 telephonic numbers natively resolving to the telecom carrier interfaces. This handles multiple strings utilizing the standard chunk POST payload system.

## Endpoint

`POST /api/trinity/phone`

## Authentication

All external bindings operate exclusively through API key resolution against user profiles.

1. **Request Body:** Securely send JSON key-mapped `"Authentication": "key"`.
2. **URL Header Parameters:** Overload endpoints `?Authentication=key`.

## Request Structure

**Headers:**
- `Content-Type: application/json`

**Body (`application/json`):**
```json
{
  "Authentication": "YOUR_API_KEY",
  "querylist": [
    "+441234567890",
    "+15551234567"
  ]
}
```

## Credit Deduction
Operations inherently execute strict credit boundaries parsing lengths relative to user bounds prior to initiating the lookup loop. Standard returns HTTP `402` denoting an aborted session due to lacking funds.

## Response Structure

Replies conform to HTTP standard `200` outputs binding TrinityResult generic interfaces paired dynamically to array bounds of PhoneSearchResults.

```json
{
  "searchMetadata": {
    "status": 200,
    "messageType": "results",
    "totalSearches": 2,
    "duration": "0.19s",
    "totalFound": 2,
    "route": "/api/trinity/phone",
    "timestamp": "1712330000000"
  },
  "resultData": {
    "results": [
      {
         // E.164 parsing formats, Line Types (Mobile/Fixed), Carrier routing bindings
      }
    ]
  },
  "scanId": 7710
}
```

## Error Responses
- **401 Unauthorized access**: API verification failed.
- **402 Insufficient credits**: Bounds exceeded user capabilities.
- **400 Bad Request**: Invalid queries passed.
