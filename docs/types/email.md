# Email Data Types

All data types serialized dynamically when using the [Email REST API](../api/email.md).
See also [Shared Data Types](shared.md).

## `EmailSearchResults`

Root generic wrapper for Email tool responses.

| Field | Type | Description |
|---|---|---|
| `type` | `string` | Statically bound to `"email"`. |
| `results` | [`SingleEmailSearchResult[]`](#singleemailsearchresult) | The distinct outputs bounded for each targeted Email format. |

## `SingleEmailSearchResult`

| Field | Type | Description |
|---|---|---|
| `email` | `string` | The structured literal evaluation representing string mapping input. |
| `sites` | [`SiteResult[]`](#siteresult) | Registered profile detections safely bounding platforms securely. |
| `domain` | [`EmailDomainCheckData`](#emaildomaincheckdata) | TLD context evaluations successfully structurally. |
| `deep` | [`DeepGhuntResult`](#deepghuntresult) | Google Workspace intelligence. *(Optional)* |
| `elapsed_ms` | `number` | Functional lag output comprehensively. |

## `SiteResult`

| Field | Type | Description |
|---|---|---|
| `name` | `string` | Target service identity. |
| `url` | `string` | Reference URL. |
| `found` | `boolean` | Success flag for profile match. |
| `description` | `string` | Metadata description of the site. *(Optional)* |
| `profile_url` | `string` | Validated target profile path. *(Optional)* |

## `EmailDomainCheckData`

| Field | Type | Description |
|---|---|---|
| `domain` | `string` | The parsed top level domain part. |
| `is_disposable` | `boolean` | Disposable provider evaluation. |
| `is_freemail` | `boolean` | Open email provider assessment. |
| `is_role_account` | `boolean` | Administrator or team alias check. |
| `has_mx_records` | `boolean` | Mail exchange reachability check. |

## `DeepGhuntResult`

Detailed output from the internal GHunt implementation for Google accounts.

| Field | Type | Description |
|---|---|---|
| `found` | `boolean` | Overall Google identity discovery indicator. |
| `email` | `string` | Matched identifier string. |
| `profile` | `Object` | Context profile keys mapping raw IDs. *(Optional)* |
| `account` | `Object` | Basic Google internal account settings. *(Optional)* |
| `maps` | `Object` | Contributor identity records on Maps. *(Optional)* |
| `photos` | `Object` | Publicly shared imagery content profiles. *(Optional)* |
| `youtube` | `Object` | Video publishing channel contexts. *(Optional)* |
| `calendar` | `Object` | Accessible event schedule mapping arrays. *(Optional)* |
| `drive` | `Object` | Content file storage sharing metadata. *(Optional)* |
| `elapsed_ms` | `number` | Dedicated execution metric. |
