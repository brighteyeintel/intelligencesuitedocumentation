# Username Data Types

All data types serialized dynamically when using the [Username REST API](../api/username.md).

## `UsernameLookupResults`

| Field | Type | Description |
|---|---|---|
| `type` | `string` | Statically bound to `"username"`. |
| `results` | [`SingleUsernameSearchResult[]`](#singleusernamesearchresult) | Format arrays extracted maps. |

## `SingleUsernameSearchResult`

| Field | Type | Description |
|---|---|---|
| `username` | `string` | Identifier representation valid map. |
| `accounts` | `Object[]` | Array extracting domain values. |
