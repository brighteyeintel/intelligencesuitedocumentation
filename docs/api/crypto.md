# Crypto REST API Documentation

The `crypto` API endpoint facilitates programmatic tracing and intelligence retrieval related to cryptocurrency blockchain wallets (BTC, ETH, etc). Supports mass inquiries per individual bulk RESTful POST requests.

## Endpoint

`POST /api/trinity/crypto`

## Authentication

Use your developer internal infrastructure API Key to securely transact. Available parsing methods for keys:

1. **Request Body (Suggested):** Pair it alongside payload inside `Authentication: "..."`.
2. **URL Search Parameters:** Assign explicit query argument parameter `?Authentication=K_100`.

## Request Structure

**Headers:**
- `Content-Type: application/json`

**Body (`application/json`):**
```json
{
  "Authentication": "YOUR_API_KEY",
  "querylist": [
    "1A1zP1eP5QGefi2DMPTfTL5SLmv7DivfNa",
    "0xDef1C0ded9bec7F1a1670819833240f027b25EfF"
  ]
}
```

## Credit Deduction
Consumes user wallet credits according to valid items pushed into the `querylist` processing queues. If bounds cannot be cleared, aborts sequence early returning HTTP status `402 Insufficient credits`.

## Response Structure

Success triggers standard HTTP `200` statuses. Wraps an encapsulated instance of TrinityResult binding CryptoSearchResults metadata.

```json
{
  "searchMetadata": {
    "status": 200,
    "messageType": "results",
    "totalSearches": 2,
    "duration": "2.40s",
    "totalFound": 2,
    "route": "/api/trinity/crypto",
    "timestamp": "1712330000000"
  },
  "resultData": {
    "results": [
      {
         // Ledger activities, unspent transaction bounds, node histories
      }
    ]
  },
  "scanId": 4410
}
```

## Error Responses
- **401 Unauthorized access**: Missing or expired Authentication.
- **402 Insufficient credits**: User quota low.
- **400 Bad Request**: Erroneous body values parsed.
