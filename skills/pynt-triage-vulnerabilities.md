---
name: pynt-triage-vulnerabilities
description: >-
  Triage Pynt vulnerability findings — list instances, check Pynt's LLM
  false-positive and business-impact analyses, mark relevance, tag, and open
  Jira tickets for the ones that matter. Use when asked to work through Pynt
  findings or turn a scan into tickets.
api: Pynt
provider: pynt
base_url: https://api.pynt.io
generated: '2026-08-27'
method: generated
source: openapi/pynt-openapi.json — every operationId below is verbatim from the contract
operations:
  - list_vulnerability_instances_v1_vulnerability_instance_get
  - find_vulnerability_instance_by_id_v1_vulnerability_instance__vulnerability_instance_id__get
  - get_false_positive_analysis_v1_scan__scan_id__false_positive_analysis_get
  - update_finding_approval_v1_scan__scan_id__false_positive_analysis__finding_id__approved_put
  - get_business_impact_analysis_v1_scan__scan_id__business_impact_analysis_get
  - update_vulnerability_instance_relevance_v1_vulnerability_instance__vulnerability_instance_id__relevance_put
  - update_vulnerability_instances_tags_v1_vulnerability_instance__vulnerability_instance_id__tags_put
  - create_ticket_jira_v1_vulnerability_instance__vulnerability_instance_id__ticket_jira_post
  - aggregate_risks_v1_endpoint_group_risks_get
---

# Triage Pynt vulnerability findings

## 1. Check the false positives FIRST

`GET /v1/scan/{scan_id}/false-positive-analysis` —
`get_false_positive_analysis_v1_scan__scan_id__false_positive_analysis_get`

Pynt runs its own LLM false-positive pass. Read it before you report anything as
a real vulnerability. Approve or reject a specific finding with
`PUT /v1/scan/{scan_id}/false-positive-analysis/{finding_id}/approved` —
`update_finding_approval_v1_scan__scan_id__false_positive_analysis__finding_id__approved_put`
(body `ApprovalUpdateRequest`).

## 2. Rank by business impact, not severity alone

`GET /v1/scan/{scan_id}/business-impact-analysis` —
`get_business_impact_analysis_v1_scan__scan_id__business_impact_analysis_get`

Approve individual findings with
`PUT /v1/scan/{scan_id}/business-impact-analysis/{finding_id}/approved` —
`update_finding_approval_v1_scan__scan_id__business_impact_analysis__finding_id__approved_put`.

## 3. Work the instance list

`GET /v1/vulnerability-instance` —
`list_vulnerability_instances_v1_vulnerability_instance_get`

Shape the list with the `filter` query parameter. **Pynt publishes no pagination
grammar** — no limit/offset, no cursor, no Link header — so on a large estate
narrow with `filter` rather than assuming you can page. See
`conventions/pynt-conventions.yml`.

Detail: `GET /v1/vulnerability-instance/{vulnerability_instance_id}` —
`find_vulnerability_instance_by_id_v1_vulnerability_instance__vulnerability_instance_id__get`.

## 4. Record your judgement

- Relevance: `PUT /v1/vulnerability-instance/{vulnerability_instance_id}/relevance`
  — `update_vulnerability_instance_relevance_v1_vulnerability_instance__vulnerability_instance_id__relevance_put`
- Tags: `PUT /v1/vulnerability-instance/{vulnerability_instance_id}/tags`
  — `update_vulnerability_instances_tags_v1_vulnerability_instance__vulnerability_instance_id__tags_put`

## 5. Ticket the ones that matter

`POST /v1/vulnerability-instance/{vulnerability_instance_id}/ticket/jira` —
`create_ticket_jira_v1_vulnerability_instance__vulnerability_instance_id__ticket_jira_post`
(body `JiraCreateTicketRequest`)

Requires a connected Jira integration
(`PUT /v1/ticketing/jira` — `connect_jira_v1_ticketing_jira_put`).

**No idempotency key exists on this API.** A retried ticket call creates a
second ticket. Confirm success before retrying.

## 6. Roll up

`GET /v1/endpoint-group/risks` — `aggregate_risks_v1_endpoint_group_risks_get`
gives aggregated risk across endpoint groups. Export with
`POST /v1/endpoint-group/export` — `generate_export_v1_endpoint_group_export_post`.
