# Mac Address Data Types

All data types serialized dynamically when using the [Mac Address REST API](../api/macaddress.md).

## `BSSIDSearchResults`

| Field | Type | Description |
|---|---|---|
| `type` | `string` | Statically bound to `"bssid"`. |
| `results` | [`SingleBSSIDSearchResult[]`](#singlebssidsearchresult) | Mappings returned format target. |

## `SingleBSSIDSearchResult`

| Field | Type | Description |
|---|---|---|
| `bssid` | `string` | Literal representation map matched. |
| `coordinates` | `Object[]` | Array extracting latitude limits. |
