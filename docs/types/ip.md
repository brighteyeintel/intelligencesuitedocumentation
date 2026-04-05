# IP Data Types

All data types serialized dynamically when using the [IP REST API](../api/ip.md).

## `IPSearchResults`

Root generic wrapper extending tool capability contexts.

| Field | Type | Description |
|---|---|---|
| `type` | `string` | Statically bound to `"ip"`. |
| `results` | [`SingleIPSearchResult[]`](#singleipsearchresult) | The distinct outputs bounded for each targeted IP format. |

## `SingleIPSearchResult`

| Field | Type | Description |
|---|---|---|
| `ip` | `string` | The literal IP matched. |
| `rir` | `string` | Regional Internet Registry handling assignments. |
| `is_bogon` | `boolean` | True if the IP is spoofed or reserved. |
| `is_mobile` | `boolean` | Cellular proxy detection status. |
| `is_satellite` | `boolean` | Indicates orbital uplink providers. |
| `is_crawler` | `boolean` | Known botnet infrastructure flag. |
| `is_datacenter` | `boolean` | Server farm matching contexts. |
| `is_tor` | `boolean` | Onion routing network evaluation output. |
| `is_proxy` | `boolean` | Anonymizing interfaces explicitly defined. |
| `is_vpn` | `boolean` | Virtual Private Network tunnel matching flag. |
| `is_abuser` | `boolean` | Generally malicious flags explicitly defined. |
| `datacenter` | [`IIPDatacenter`](#iipdatacenter) | DC details if applicable. |
| `company` | [`IIPCompany`](#iipcompany) | Operating organization details. |
| `abuse` | [`IIPAbuse`](#iipabuse) | Reporting authority boundaries. |
| `asn` | [`IIPAsn`](#iipasn) | Autonomous system number routing domains. |
| `location` | [`IIPLocation`](#iiplocation) | Geo-mapping formats. |
| `elapsed_ms` | `number` | Internal execution lags in milliseconds. |
| `drone_bl` | [`IDroneBLLookup`](#idronebllookup) | RTBH (Real-Time Blackhole) API mapping flags. |
| `threat_fox` | [`ThreatFoxIOCResult[]`](#threatfoxiocresult) | Malicious contexts against threat platforms. |

## `IIPDatacenter`

| Field | Type | Description |
|---|---|---|
| `datacenter` | `string` | Label identifying infrastructures. |
| `network` | `string` | Range assigned. |
| `country` | `string` | DC location boundaries. |
| `region` | `string` | State or region names. |
| `city` | `string` | Specific urbanization contexts. |

## `IIPCompany`

| Field | Type | Description |
|---|---|---|
| `name` | `string` | Firm context dynamically retrieved. |
| `abuser_score` | `string` | Metrics mapped explicitly. |
| `domain` | `string` | Official URL endpoints. |
| `type` | `string` | Category descriptions. |
| `network` | `string` | ASN mappings. |
| `whois` | `string` | Contact points smartly outputting records. |

## `IIPAbuse`

| Field | Type | Description |
|---|---|---|
| `name` | `string` | Point of contact. |
| `address` | `string` | Formatting mailing context. |
| `email` | `string` | RFC representation reporting email. |
| `phone` | `string` | Contact number explicitly defined. |

## `IIPAsn`

| Field | Type | Description |
|---|---|---|
| `asn` | `number` | The numerical identifier. |
| `abuser_score` | `string` | Threat intelligence score. |
| `route` | `string` | CIDR representation. |
| `descr` | `string` | Verbose label. |
| `country` | `string` | The 2-letter country code. |
| `active` | `boolean` | Operational flag. |
| `org` | `string` | Organization mapping (optional). |
| `domain` | `string` | Associated domain (optional). |
| `abuse` | `string` | Associated abuse contact (optional). |
| `type` | `string` | Category (optional). |
| `created` | `string` | Creation timestamp. |
| `updated` | `string` | Update timestamp (optional). |
| `rir` | `string` | Regional Internet Registry (optional). |
| `whois` | `string` | Whois server reference (optional). |

## `IIPLocation`

| Field | Type | Description |
|---|---|---|
| `is_eu_member` | `boolean` | Jurisdictional evaluation of EU membership. |
| `calling_code` | `string` | Dial code for the region. |
| `currency_code` | `string` | Currency format code. |
| `continent` | `string` | Continent mapping. |
| `country` | `string` | Country mapping. |
| `country_code` | `string` | 2-letter country code. |
| `state` | `string` | State/province mapping. |
| `city` | `string` | Urban center. |
| `latitude` | `number` | Geolocation latitude point. |
| `longitude` | `number` | Geolocation longitude point. |
| `zip` | `string` | Zip/Postal code mapping. |
| `timezone` | `string` | Local timezone specifier. |
| `local_time` | `string` | Contextual string for time mappings. |
| `local_time_unix` | `number` | Epoch evaluation for location. |
| `is_dst` | `boolean` | Daylight savings flag. |

## `IDroneBLLookup`

| Field | Type | Description |
|---|---|---|
| `found` | `boolean` | Flag indicating inclusion in DroneBL databases. |
| `url` | `string` | Lookup reference endpoint (optional). |

## `ThreatFoxIOCResult`

| Field | Type | Description |
|---|---|---|
| `id` | `string` | Unique identifier instance. |
| `ioc` | `string` | Identifier mapping literal. |
| `threat_type` | `string` | Evaluated category explicitly. |
| `threat_type_desc` | `string` | Details of the category. |
| `ioc_type` | `string` | Type format descriptor. |
| `ioc_type_desc` | `string` | Details of type. |
| `malware` | `string` | Associated malware strains. |
| `malware_printable` | `string` | Rendered format instance. |
| `malware_alias` | `string` | Common names mapped. |
| `malware_malpedia` | `string` | Malpedia ID reference. |
| `confidence_level` | `number` | Scoring algorithms outputs. |
| `first_seen` | `string` | Discovery mapping. |
| `last_seen` | `string` | Most recent timestamp (optional). |
| `reference` | `string` | Proof linkages (optional). |
| `reporter` | `string` | Reporting identity mapping. |
| `tags` | `string` | Search context array string mappings (optional). |
| `malware_samples` | [`ThreatFoxMalwareSample[]`](#threatfoxmalwaresample) | Contexts natively bounds. |

## `ThreatFoxMalwareSample`

| Field | Type | Description |
|---|---|---|
| `time_stamp` | `string` | Encounter evaluations safely defined. |
| `md5_hash` | `string` | Cryptographic bounds explicitly mapped. |
| `sha256_hash` | `string` | Secure string formatting cleanly. |
| `malware_bazar` | `string` | ID contexts nicely. |
