# Officers REST API Documentation

The `officers` API endpoint provides programmatic access to search directories linking to registered corporate officers and entity directors. It integrates multiple searches into one optimized bulk POST array request.

## Endpoint

`POST /api/trinity/officers`

## Authentication

Identify access origin to backend infrastructure securely using a registered API Key.

1. **Request Body (Primary):** Deliver `Authentication` field mappings in the initial payload format.
2. **URL Search Parameters:** Send directly encoded via URL parameters: `?Authentication=your_api_token`.

## Request Structure

**Headers:**
- `Content-Type: application/json`

**Body (`application/json`):**
```json
{
  "Authentication": "YOUR_API_KEY",
  "querylist": [
    "John Doe",
    "Jane Smith"
  ]
}
```

## Credit Deduction
Credits are automatically deduced at a standard computational rate matching the bounds evaluated. A typical sequence assesses `querylist.length`. Requests immediately throw `402 Insufficient credits` upon deficient balances to prevent over-subscription runtime failures.

## Response Structure

Upon evaluation, issues an HTTP `200` mapping TrinityResult metadata and its internal OfficerSearchResults payload formats securely.

```json
{
  "searchMetadata": {
    "status": 200,
    "messageType": "results",
    "totalSearches": 2,
    "duration": "2.44s",
    "totalFound": 2,
    "route": "/api/trinity/officers",
    "timestamp": "1712330000000"
  },
  "resultData": {
    "results": [
      {
         // Director linkage metadata, appointment spans, associations
      }
    ]
  },
  "scanId": 4833
}
```

## Error Responses
- **401 Unauthorized access**: Lacking sufficient API credentials.
- **402 Insufficient credits**: Account funds too low.
- **400 Bad Request**: Erroneous body values parsed.
