# Crypto Data Types

All data types serialized dynamically when using the [Crypto REST API](../api/crypto.md).

## `CryptoSearchResults`

| Field | Type | Description |
|---|---|---|
| `type` | `string` | Statically bound to `"crypto"`. |
| `results` | [`SingleCryptoSearchResult[]`](#singlecryptosearchresult) | The mapped wallets. |

## `SingleCryptoSearchResult`

| Field | Type | Description |
|---|---|---|
| `address` | `string` | Target address ID. |
| `total_received` | `number` | The total quantity of received funds. |
| `total_sent` | `number` | The total quantity of sent funds. |
| `balance` | `number` | Confirmed balance. |
| `unconfirmed_balance` | `number` | Pending balance awaiting blocks. |
| `final_balance` | `number` | Account total. |
| `n_tx` | `number` | Transaction quantity. |
| `unconfirmed_n_tx` | `number` | Pending operations count. |
| `final_n_tx` | `number` | All valid transactions. |
| `transactions` | [`ICryptoTransaction[]`](#icryptotransaction) | Extracted ledger payments array. |
| `unspent` | [`ICryptoUnspent[]`](#icryptounspent) | Associated hold accounts mapped. |

## `ICryptoTransaction`

| Field | Type | Description |
|---|---|---|
| `hash` | `string` | Internal transaction identifier. |
| `confirmations` | `number` | Validated ledger confirmations. |
| `size` | `number` | Byte payload identifier. |
| `vsize` | `number` | Virtual weight metric. |
| `version` | `number` | Block logic format. |
| `lock_time` | `number` | Verification lock delay timeout. |
| `time` | `number` | Processed Unix timestamp map. |
| `inputs` | `Object[]` | Funds sent into operation limits. |
| `outputs` | `Object[]` | Resulting target addresses list. |
| `fee` | `number` | Paid extraction amount. |

## `ICryptoUnspent`

| Field | Type | Description |
|---|---|---|
| `tx_hash` | `string` | Origin event ledger mark. |
| `tx_output_n` | `number` | Specific target count pointer. |
| `value` | `number` | Held numeric value limit. |
| `confirmations` | `number` | Ledger confirmation metric count. |
| `script` | `string` | Execution format variable map. |
