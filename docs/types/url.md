# URL Data Types

All data types serialized dynamically when using the [URL REST API](../api/url.md).
See also [Shared Data Types](shared.md) and [IP Data Types](ip.md).

## `URLSearchResults`

Root generic wrapper for URL tool responses.

| Field | Type | Description |
|---|---|---|
| `type` | `string` | Statically bound to `"url"`. |
| `results` | [`SingleURLSearchResult[]`](#singleurlsearchresult) | The distinct outputs bounded for each targeted URL format. |

## `SingleURLSearchResult`

| Field | Type | Description |
|---|---|---|
| `url` | `string` | The literal URL input processed. |
| `parsed` | `Object` | Context dictionary splitting domain, protocol, path, etc. |
| `ip` | [`SingleIPSearchResult`](ip.md#singleipsearchresult) | Details populated by resolving the IP address of the domain. *(Optional)* |
| `dns` | [`IDNSRecord[]`](#idnsrecord) | Standard resolution mapping explicit arrays. *(Optional)* |
| `cert` | [`ICertificateInfo`](#icertificateinfo) | Extracted X509 certificate variables. *(Optional)* |
| `wayback` | [`IWaybackSnapshot[]`](#iwaybacksnapshot) | Historical archive contexts mapping timestamps. *(Optional)* |
| `tranco` | [`ITrancoRank`](#itrancorank) | Traffic rank metrics. *(Optional)* |
| `html` | [`IHTMLAnalysis`](#ihtmlanalysis) | Tags and title output from HTML scraping. *(Optional)* |

## `IDNSRecord`

| Field | Type | Description |
|---|---|---|
| `name` | `string` | Evaluation reference name. |
| `type` | `number` | Resource record definitions bounds (e.g. 1 for A, 15 for MX). |
| `class` | `number` | Representation class codes. |
| `ttl` | `number` | Time to live mappings. |
| `address` | `string` | The IP resolution. *(Optional)* |
| `data` | `string` | Generic context if not A-type. *(Optional)* |
| `exchange` | `string` | Mail Exchange target server boundaries. *(Optional)* |
| `priority` | `number` | Value indicating MX preference. *(Optional)* |
| `nsname` | `string` | Name server hostname mapping. *(Optional)* |
| `primary` | `string` | SOA definition of primary nameserver. *(Optional)* |
| `admin` | `string` | SOA point of contact dynamically evaluated. *(Optional)* |
| `serial` | `number` | SOA sequence flag outputs. *(Optional)* |
| `refresh` | `number` | SOA refresh interval. *(Optional)* |
| `retry` | `number` | SOA retry interval. *(Optional)* |
| `expiration` | `number` | SOA failover times mapped. *(Optional)* |
| `minimum` | `number` | SOA TTL explicit defaults explicitly. *(Optional)* |

## `ICertificateInfo`

| Field | Type | Description |
|---|---|---|
| `issuer` | `string` | Certificate Authority. |
| `subject` | `string` | Common Name bound. |
| `valid_from` | `string` | Start validation boundary. |
| `valid_to` | `string` | Expiration validation boundary. |
| `serial_number` | `string` | Fingerprint identifiers cleanly mapped. |
| `subject_alt_names` | `string[]` | SAN extensions gracefully defined. *(Optional)* |

## `IWaybackSnapshot`

| Field | Type | Description |
|---|---|---|
| `url` | `string` | Lookup mapping. |
| `timestamp` | `string` | Historical mapped values cleanly explicit. |
| `status` | `string` | HTTP evaluation at snapshot time. |
| `digest` | `string` | Internal checksum dynamically bounds. |

## `ITrancoRank`

| Field | Type | Description |
|---|---|---|
| `domain` | `string` | Evaluated domain. |
| `rank` | `number` | Global traffic metrics securely natively mappings. |
| `date` | `string` | Rank execution string representation. *(Optional)* |

## `IHTMLAnalysis`

| Field | Type | Description |
|---|---|---|
| `title` | `string` | Page heading mapping. |
| `meta_tags` | `Object` | Key-value pairs of extracted HTML meta tags. *(Optional)* |
