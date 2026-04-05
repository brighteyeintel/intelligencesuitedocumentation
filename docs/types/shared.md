# Shared Response Types

Many of the APIs in Trinity return standardized wrapping structures.

## `TrinityResult`

The base layout wrapping all successful response payloads natively.

| Field | Type | Description |
|---|---|---|
| `searchMetadata` | [`SearchMetadata`](#searchmetadata) | Contextual runtime variables evaluating standard metrics. |
| `resultData` | `Object` | Tool-specific responses bound here natively. |
| `scanId` | `string` | The relational internal representation database scan id identifier. *(Nullable)* |
| `source` | `string` | Source origin. Typically `"api"`. *(Nullable)* |

## `SearchMetadata`

Contextual properties mapping computational lag.

| Field | Type | Description |
|---|---|---|
| `status` | `number` | HTTP Status values resolving state (usually 200). |
| `messageType` | `string` | Payload format identity (e.g. `"results"`). |
| `route` | `string` | Fully qualified endpoint path accessed. |
| `query` | `string` | Array value mapped back as one concatenated literal string query log. |
| `timestamp` | `string` | ISO string mapping internal date timestamps correctly. |
| `duration` | `string` | Total computational elapsed lag represented natively in seconds (e.g., `1.52s`). |
| `totalSearches` | `number` | Represents queries initially evaluated. |
| `totalFound` | `number` | Represents queries which actually cleared validation returning positive yields. |
