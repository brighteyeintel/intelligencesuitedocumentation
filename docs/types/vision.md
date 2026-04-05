# Vision Data Types

All data types serialized dynamically when using the [Vision REST API](../api/vision.md).
See also [Shared Data Types](shared.md).

## `VisionSearchResults`

Root wrapper for Google Vision queries.

| Field | Type | Description |
|---|---|---|
| `type` | `string` | Statically bound to `"vision"`. |
| `results` | [`SingleVisionSearchResult[]`](#singlevisionsearchresult) | Image analysis output. |

## `SingleVisionSearchResult`

| Field | Type | Description |
|---|---|---|
| `labels` | `string[]` | Confidence evaluated array items identifying objects. |
| `text` | `string` | OCR rendered values parsed from images. *(Optional)* |
| `faces` | `string[]` | Emotional context descriptions identified. *(Optional)* |
| `landmarks` | [`IVisionLandmark[]`](#ivisionlandmark) | Geographic coordinate structures. |
| `logos` | [`IVisionLogo[]`](#ivisionlogo) | Commercial entities matched. |
| `web` | [`IVisionWebDetection`](#ivisionwebdetection) | Interconnected entities matched across Google index. *(Optional)* |

## `IVisionLandmark`

| Field | Type | Description |
|---|---|---|
| `name` | `string` | Entity label context mapping. |
| `latitude` | `number` | Float coordinate representation for latitude. |
| `longitude` | `number` | Float coordinate representation for longitude. |

## `IVisionLogo`

| Field | Type | Description |
|---|---|---|
| `description` | `string` | Label representations correctly bounded. |
| `score` | `number` | Float variable determining match validity. |

## `IVisionWebDetection`

| Field | Type | Description |
|---|---|---|
| `webEntities` | `string[]` | Correlated concepts defined array. *(Optional)* |
| `fullMatchingImages` | `string[]` | Duplicate copies mapped explicitly. *(Optional)* |
| `partialMatchingImages` | `string[]` | Similar formats seamlessly mapped. *(Optional)* |
| `pagesWithMatchingImages` | `string[]` | Host endpoints containing similar graphics. *(Optional)* |
| `visuallySimilarImages` | `string[]` | Visual matches mapped dynamically. *(Optional)* |
