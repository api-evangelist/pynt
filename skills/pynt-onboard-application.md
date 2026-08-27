---
name: pynt-onboard-application
description: >-
  Register a new application in Pynt, attach an API discovery source
  (OpenAPI/Swagger, Postman collection, API gateway, code repo or live traffic),
  and put it on a recurring scan schedule. Use when adding a new API estate to
  Pynt for the first time.
api: Pynt
provider: pynt
base_url: https://api.pynt.io
generated: '2026-08-27'
method: generated
source: openapi/pynt-openapi.json — every operationId below is verbatim from the contract
operations:
  - create_application_v1_application_put
  - upsert_data_source_v1_application__application_id__data_sources_post
  - get_data_source_v1_application__application_id__data_sources__data_source_type__get
  - create_endpoints_v1_application__application_id__endpoints_post
  - create_scan_schedule_v1_application__application_id__scan_schedule_post
  - update_scan_schedule_state_v1_application__application_id__scan_schedule__scan_schedule_id__state_patch
  - get_single_application_metrics_v1_application__application_id__metrics_get
---

# Onboard an application into Pynt

An **application** is Pynt's unit of an API estate. Everything else — sources,
endpoints, scans, findings, reports — hangs off it. See
`data-model/pynt-data-model.yml`.

## 1. Create the application

`PUT /v1/application` — `create_application_v1_application_put`

Body is `CreateApplicationRequest`. `name` is required and must be at least 3
characters. Optional: `assignee_id`, `tags[]`, `poid` (UUID).

Note the verb: creation is a **PUT**, not a POST. Update is
`POST /v1/application/{application_id}`
(`update_application_v1_application__application_id__post`) — the reverse of the
usual convention. Do not assume.

## 2. Attach a discovery source

`POST /v1/application/{application_id}/data-sources` —
`upsert_data_source_v1_application__application_id__data_sources_post`
(body `UpdateDataSourceRequest`)

Pynt's documented source categories are API documentation (Swagger/OpenAPI,
Postman collection), API gateways (AWS, Azure, Kong, GCP, Gravitee), code
repositories, testing, and live traffic (eBPF, AWS traffic mirroring).

Read it back with
`GET /v1/application/{application_id}/data-sources/{data_source_type}` —
`get_data_source_v1_application__application_id__data_sources__data_source_type__get`.

To seed endpoints directly instead:
`POST /v1/application/{application_id}/endpoints` —
`create_endpoints_v1_application__application_id__endpoints_post`.

## 3. Schedule recurring scans

`POST /v1/application/{application_id}/scan-schedule` —
`create_scan_schedule_v1_application__application_id__scan_schedule_post`
(body `CreateScanScheduleRequest`; the contract supports day-of-week,
day-interval and once-only specs).

## 4. Confirm

`GET /v1/application/{application_id}/metrics` —
`get_single_application_metrics_v1_application__application_id__metrics_get`

## Undoing this

- A schedule can be **disabled** rather than deleted:
  `PATCH /v1/application/{application_id}/scan-schedule/{scan_schedule_id}/state`
  — `update_scan_schedule_state_v1_application__application_id__scan_schedule__scan_schedule_id__state_patch`.
  This is the only soft-reversal in the contract.
- `DELETE /v1/application/{application_id}` and
  `DELETE /v1/application/{application_id}/data-sources/{data_source_type}` are
  **irreversible**. There is no restore or undelete operation anywhere in the
  Pynt API. Confirm with the human before either. See
  `conventions/pynt-conventions.yml`.
