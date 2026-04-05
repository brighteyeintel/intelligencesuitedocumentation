# Telephone Data Types

All data types serialized dynamically when using the [Phone REST API](../api/phone.md).

## `PhoneSearchResults`

| Field | Type | Description |
|---|---|---|
| `type` | `string` | Statically bound to `"phone"`. |
| `results` | [`SinglePhoneSearchResult[]`](#singlephonesearchresult) | Evaluated entity mappings format. |

## `SinglePhoneSearchResult`

| Field | Type | Description |
|---|---|---|
| `phone_number` | `string` | Value passed logic output. |
| `places` | `Object[]` | External maps reference array. |
| `locations` | `Object[]` | Evaluated coordinate variable map. |
