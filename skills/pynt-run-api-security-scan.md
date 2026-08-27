---
name: pynt-run-api-security-scan
description: >-
  Run a Pynt API security scan against a registered application, wait for it to
  finish, and read the findings. Use when asked to security-test an API,
  re-scan an application after a change, or check what a scan found.
api: Pynt
provider: pynt
base_url: https://api.pynt.io
generated: '2026-08-27'
method: generated
source: openapi/pynt-openapi.json — every operationId below is verbatim from the contract
operations:
  - list_applications_v1_application_get
  - run_scan_v1_scan_run_remote_scan_post
  - get_all_running_scans_v1_scan_running_get
  - get_scan_by_id_v1_scan__scan_id__summary_get
  - abort_scan_v1_scan__scan_id__abort_post
  - get_report_v1_scan__scan_id__report_get
---

# Run a Pynt API security scan

**A Pynt scan is an active security test.** It sends attack traffic at the target
API. Confirm with the human which application is being scanned and that the
target is one they are authorised to test, before step 2.

## 1. Find the application

`GET /v1/application` — `list_applications_v1_application_get`

Returns `ApplicationListItemOut` items carrying `app_id`, `name`, `assignee_id`
and `last_scan_id`. Match on `name` and keep the `app_id`; every later call
needs it.

If the application does not exist yet, use the
`pynt-onboard-application` skill first.

## 2. Start the scan

`POST /v1/scan/run-remote-scan` — `run_scan_v1_scan_run_remote_scan_post`

Body is `RunRemoteScanRequestBody`. Required: `api_key`, `collection_to_test`,
`application_id` (UUID). Optional: `environment_name`.

For a HAR-based scan use `POST /v1/scan/run-remote-har-scan`
(`run_har_scan_v1_scan_run_remote_har_scan_post`) instead.

**There is no dry-run and no idempotency key on this API.** A retried POST
starts a second scan. If the response is ambiguous, poll step 3 rather than
retrying.

## 3. Poll until it finishes

`GET /v1/scan/running` — `get_all_running_scans_v1_scan_running_get`, or
`GET /v1/scan/{scan_id}/summary` — `get_scan_by_id_v1_scan__scan_id__summary_get`

Poll the summary. Back off between polls — Pynt publishes no rate limits and no
`Retry-After`, so use a conservative fixed interval (30s) rather than tight
looping. See `rate-limits/pynt-rate-limits.yml`.

## 4. Abort if you need to stop

`POST /v1/scan/{scan_id}/abort` — `abort_scan_v1_scan__scan_id__abort_post`

This is the only reversal on this flow. Pynt states **no window** for it and no
guarantee about what a partially completed active test leaves behind on the
target. Aborting is not the same as never having scanned.

## 5. Read the results

`GET /v1/scan/{scan_id}/report` — `get_report_v1_scan__scan_id__report_get`

Then enrich with Pynt's LLM analyses before reporting anything to a human:

- `GET /v1/scan/{scan_id}/false-positive-analysis` —
  `get_false_positive_analysis_v1_scan__scan_id__false_positive_analysis_get`
- `GET /v1/scan/{scan_id}/business-impact-analysis` —
  `get_business_impact_analysis_v1_scan__scan_id__business_impact_analysis_get`

Do not present raw findings as confirmed vulnerabilities without checking the
false-positive analysis first.

## Errors

Only `422` is declared in the contract. `401` (`{"detail":"Unauthorized"}`) and
`404` (`{"detail":"Not Found"}`) were confirmed live but appear on zero
operations, so handle them defensively. On `422`, read `detail[].loc` for the
offending field and `detail[].msg` for the constraint — the request as sent will
never succeed, so fix it rather than retrying. See
`errors/pynt-problem-types.yml`.

## Auth

Send one of `X-API-Key`, `Authorization`, or `X-System-API-Key`; some operations
also want `X-Organization-ID`. See `authentication/pynt-authentication.yml`.
