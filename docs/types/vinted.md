# Vinted Data Types

All data types serialized dynamically when using the [Vinted REST API](../api/vinted.md).

## `VintedSearchResults`

Root wrapper for Vinted queries.

| Field | Type | Description |
|---|---|---|
| `type` | `string` | Statically bound to `"vinted"`. |
| `results` | [`VintedUserResult[]`](#vinteduserresult) | Evaluation contexts for each queried username. |

## `VintedUserResult`

| Field | Type | Description |
|---|---|---|
| `id` | `number` | Internal platform user ID. |
| `login` | `string` | Account nickname string. |
| `profile_url` | `string` | Direct web endpoint interface URL. |
| `real_name` | `string` | Identity mapping properly. *(Optional)* |
| `gender` | `string` | Profile indication label (e.g. M, F). *(Optional)* |
| `birthday` | `string` | DOB format output. *(Optional)* |
| `item_count` | `number` | Products currently live natively. |
| `given_item_count` | `number` | Value indicating distinct donations. |
| `taken_item_count` | `number` | Metrics representing taken variables. |
| `followers_count` | `number` | Social graph metric array length. |
| `following_count` | `number` | Accounts explicitly followed. |
| `positive_feedback_count` | `number` | Review metrics mapping positive scores. |
| `neutral_feedback_count` | `number` | Review metrics mapping neutral scores. |
| `negative_feedback_count` | `number` | Review metrics mapping negative scores. |
| `meetings_count` | `number` | Physical meetup occurrences. |
| `photo` | `string` | Avatar link representations. *(Optional)* |
| `last_loged_on` | `string` | Most recent access flag date. *(Optional)* |
| `city` | `string` | Operating region organically formatted. *(Optional)* |
| `country_id` | `number` | Platform regional identifier code. *(Optional)* |
| `country_code` | `string` | Alpha ISO string (e.g. `"FR"`, `"UK"`). *(Optional)* |
| `is_business_account` | `boolean` | Pro seller representation indicator. |
| `business_account` | `Object` | Extensive corporate structures. *(Optional)* |
| `feedback_reputation` | `number` | Evaluated composite star rating decimal. |
| `items` | [`VintedProduct[]`](#vintedproduct) | Products extracted cleanly explicitly. *(Optional)* |

## `VintedProduct`

| Field | Type | Description |
|---|---|---|
| `id` | `number` | Item instance database identifier. |
| `title` | `string` | Name context correctly mapped. |
| `price` | `string` | Asking value representation. |
| `currency` | `string` | Money mapping explicitly cleanly. |
| `is_visible` | `boolean` | Live status explicitly effectively correctly evaluated. |
| `discount_id` | `number` | Sales campaign mapped natively. *(Optional)* |
| `size_title` | `string` | Fitting descriptors. *(Optional)* |
| `brand_title` | `string` | Corporate mark text explicitly. *(Optional)* |
| `status` | `string` | Quality metric representation. |
| `color1` | `string` | Primary visual descriptor. *(Optional)* |
| `color2` | `string` | Secondary shade evaluation context. *(Optional)* |
| `catalog_id` | `number` | Category representation organically appropriately mapped. *(Optional)* |
| `url` | `string` | Dedicated hyperlink targeting the item. |
| `photos` | `string[]` | Graphic link mapping outputs array explicitly. |
