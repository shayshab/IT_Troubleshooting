# Incident Response Playbook (IT Ops)

Concise guide for assessing, containing, communicating, and resolving incidents.

## Severity & Ownership

- P1: Org‑wide outage or critical risk → Incident Commander (IC) + Technical Lead + Comms. Updates every 15–30 min.
- P2: Major impact to team(s) → IC + TL. Updates hourly.
- P3/P4: Standard support; track in ticket.

## Phases

1) Detect & Triage: confirm scope, gather evidence, open ticket, set severity, page on‑call.
2) Contain: stop the bleeding with safe mitigations (feature flags, rollback, route around).
3) Eradicate/Remediate: fix root cause or implement durable workaround.
4) Recover: verify services, monitor KPIs, and close user impact.
5) Review: capture timeline, root cause, and prevention; file follow‑ups.

## Roles

- Incident Commander: drives process, timeboxes, updates stakeholders.
- Technical Lead(s): diagnose and fix; own workstream notes.
- Communications: craft status updates, customer/internal notices.

## Communications

- Single source of truth: incident channel/ticket. Status page if customer‑facing.
- Update cadence per severity; use clear, non‑blaming language.

## Evidence & Tools

- Timestamps, error codes, screenshots, logs, dashboards, change history.
- Keep a log of actions and decisions with owners and timestamps.

## Closure Criteria

- Impact resolved, KPIs normal, monitoring alerts quieted, stakeholders notified, actions assigned with owners/due dates.

