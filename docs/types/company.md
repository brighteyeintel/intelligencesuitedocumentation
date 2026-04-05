# Company Data Types

All data types serialized dynamically when using the [Companies House REST API](../api/company.md).

## `CompanyToolResponse`

| Field | Type | Description |
|---|---|---|
| `type` | `string` | Statically bound to `"companieshouse"`. |
| `results` | [`UnifiedResult[]`](#unifiedresult) | Mixed array for query types. |

## `UnifiedResult`

This implements the combined format returned by the proxy API.

| Field | Type | Description |
|---|---|---|
| `searchType` | `string` | `"companies"` or `"officers"`. |
| `company` | [`CompanyProfileResponse`](#companyprofileresponse) | Data populated if companies match. *(Optional)* |
| `officer` | `Object` | Data populated if officers match. *(Optional)* |

## `CompanyProfileResponse`

| Field | Type | Description |
|---|---|---|
| `company_number` | `string` | Registration ID. |
| `company_status` | `string` | Legal operational flag index. |
| `title` | `string` | Formal title reference. |
| `company_type` | `string` | Registration category text format. |
| `address_snippet` | `string` | Condensed contact format location. |
| `date_of_creation` | `string` | Starting valid registration mark. |
| `date_of_cessation` | `string` | Ending valid reference time. *(Optional)* |
| `links` | `Object` | Context dictionary. |
| `address` | `Object` | City and line contexts. |
| `matches` | `Object` | Title regex matched fragments. |
| `description` | `string` | Legal format. *(Optional)* |
| `description_identifier` | `string[]` | Formats arrays. *(Optional)* |
| `kind` | `string` | API classification mapping. |
| `snippet` | `string` | Result preview values block. |

## `CompanyProfile`

Used by direct lookups.

| Field | Type | Description |
|---|---|---|
| `company_name` | `string` | Label reference matching value. |
| `company_number` | `string` | Target ID limit. |
| `company_status` | `string` | Flag indicating closure checks. |
| `company_status_detail` | `string` | Added variable information text. *(Optional)* |
| `date_of_creation` | `string` | Open time reference index. |
| `registered_office_address` | `Object` | Specific physical mapping. |
| `sic_codes` | `string[]` | Trade class evaluation. |
| `previous_company_names` | `Object[]` | Alternate IDs recorded before. *(Optional)* |
| `has_been_liquidated` | `boolean` | Insolvency indicator. *(Optional)* |
| `has_insolvency_history` | `boolean` | Legal variable mapping boolean. *(Optional)* |
| `has_charges` | `boolean` | Debt logic mapping variables. *(Optional)* |
| `undeliverable_registered_office_address` | `boolean` | Contact error evaluation output. *(Optional)* |
| `branch_company_details` | `Object` | Reference mapping limits. *(Optional)* |
| `foreign_company_details` | `Object` | International contexts values limits. *(Optional)* |
| `links` | `Object` | Associated URL limits array. |
