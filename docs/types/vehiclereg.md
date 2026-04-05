# Vehicle Registration Data Types

All data types serialized dynamically when using the [Vehicle Reg REST API](../api/vehiclereg.md).

## `VehicleRegSearchResults`

| Field | Type | Description |
|---|---|---|
| `type` | `string` | Statically bound to `"vehicle_reg"`. |
| `results` | [`SingleVehicleRegResult[]`](#singlevehicleregresult) | Values mapping extraction queries. |

## `SingleVehicleRegResult`

| Field | Type | Description |
|---|---|---|
| `registration` | `string` | Number plate formats matched. |
| `make` | `string` | Corporate identity mark string. |
| `model` | `string` | Class formats. *(Optional)* |
| `colour` | `string` | Graphic map format. *(Optional)* |
| `fuel_type` | `string` | Engine mark formats limits. *(Optional)* |
| `engine_capacity` | `number` | Size flag limits explicitly. *(Optional)* |
| `year_of_manufacture` | `number` | Execution creation values limits. *(Optional)* |
| `motData` | `Object` | Complex MOT extraction map. *(Optional)* |
| `legacyDvla` | `Object` | Fallback parameter mapping. *(Optional)* |
| `stolen_status` | `string` | Status evaluating flag variables. *(Optional)* |

## `VehicleWithMotResponse`

| Field | Type | Description |
|---|---|---|
| `registration` | `string` | Registration number. |
| `make` | `string` | Manufacturer string. |
| `model` | `string` | Vehicle model string. |
| `motTests` | `Array` | Array of MOT Tests (DVSA, DVA_NI, or CVS). |
| `hasOutstandingRecall` | `string` | Enum indicating recall status. |

## `DVSAMotTest`

| Field | Type | Description |
|---|---|---|
| `completedDate` | `string` | Date of test. |
| `testResult` | `string` | Passed or Failed. |
| `odometerValue` | `string` | Mileage limit. |
| `defects` | `Array` | Array of defects. |

## `Defect`

| Field | Type | Description |
|---|---|---|
| `text` | `string` | Defect reason text. |
| `type` | `string` | Severity enum limit. |
| `dangerous` | `boolean` | Flag for dangerous limit. |

## `NewRegVehicleResponse`

| Field | Type | Description |
|---|---|---|
| `registration` | `string` | Registration number. |
| `make` | `string` | Manufacturer string. |
| `model` | `string` | Vehicle model string. |
| `motTestDueDate` | `string` | Date MOT is due. |
| `hasOutstandingRecall` | `string` | Enum indicating recall status. |

## `DVANIMotTest`

Northern Ireland MOT test data.

| Field | Type | Description |
|---|---|---|
| `completedDate` | `string` | Date of test. |
| `testResult` | `string` | Passed or Failed. |
| `odometerValue` | `string` | Mileage limit. |

## `CVSMotTest`

Commercial Vehicle Services MOT test data.

| Field | Type | Description |
|---|---|---|
| `completedDate` | `string` | Date of test. |
| `testResult` | `string` | Passed or Failed. |
| `location` | `string` | Location of test. |
| `defects` | `Array` | Array of defects. |
