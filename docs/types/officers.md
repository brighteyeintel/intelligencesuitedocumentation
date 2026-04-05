# Officer Data Types

Data types serialized dynamically when using the [Officers REST API](../api/officers.md).
See also [Company Data Types](company.md).

## `OfficerListResponse`

| Field | Type | Description |
|---|---|---|
| `active_count` | `number` | Count of currently practicing humans. |
| `resigned_count` | `number` | Count of past entities. |
| `total_results` | `number` | Array magnitude limit. |
| `items` | [`OfficerItem[]`](#officeritem) | Entity records extracted explicitly. |

## `OfficerItem`

| Field | Type | Description |
|---|---|---|
| `name` | `string` | Identification variable matched format. |
| `officer_role` | `string` | Position indicator logic limits. |
| `appointed_on` | `string` | Placement execution logic timestamp. |
| `resigned_on` | `string` | Exit reference variable mappings. *(Optional)* |
| `nationality` | `string` | Origin label format context. *(Optional)* |
| `country_of_residence` | `string` | Locale label array identifier. *(Optional)* |
| `date_of_birth` | `Object` | Object holding month integer values. *(Optional)* |
| `occupation` | `string` | Activity mark context representation. *(Optional)* |
| `address` | `Object` | Property string variable mappings. |
| `links` | `Object` | Reference contexts values mapped. |
