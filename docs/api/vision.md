# Vision REST API Documentation

The `vision` API endpoint allows developers to programmatically access Google Vision tool, utilizing advanced image classification algorithms over a RESTful POST hook.

## Endpoint

`POST /api/trinity/vision`

## Authentication

All internal Trinity APIs require authentication. You must provide a valid API key, which is associated with your user account. There are two ways to authenticate:

1. **Request Body:** Include an `Authentication` key in the JSON body.
2. **URL Parameter:** Append `?Authentication=secret` to the endpoint.

## Request Structure

Unlike other text-driven bulk query endpoints in Trinity APIs which read arrays of `querylist`, the Vision tool requires an `image` key mapping a formatted Base64 image string.

**Headers:**
- `Content-Type: application/json`

**Body (`application/json`):**
```json
{
  "Authentication": "YOUR_API_KEY",
  "image": "data:image/jpeg;base64,/9j/4AAQSkZJRgABAQ..."
}
```

## Credit Deduction
Each API request deducts exactly 1 credit from your user account. Balance must be >= 1. Returns a `402` otherwise.

## Response Structure

The endpoint returns HTTP Status `200` alongside a full TrinityResult wrapping a VisionSearchResults structure containing the ML findings payload.

```json
{
  "searchMetadata": {
    "status": 200,
    "messageType": "results",
    "totalSearches": 1,
    "duration": "1.30s",
    "totalFound": 1,
    "route": "/api/trinity/vision",
    "timestamp": "1712330000000"
  },
  "resultData": {
    "results": [
      {
         // Analysis result containing localized objects, faces, optical labels, etc.
      }
    ]
  },
  "scanId": 2420
}
```

## Error Responses
- **401 Unauthorized access**: Missing, invalid or expired authentication API key.
- **402 Insufficient credits**: Credit balance <= 0.
- **500 Internal Server Error**: Malformed Base64 representation.
