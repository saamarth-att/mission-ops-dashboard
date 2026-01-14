# Mission Ops Dashboard – Architecture (Draft)

## Goal
Common Operating Picture (map) + Alert Triage Inbox for operational decision-making.

## Roles
- Analyst: view-only
- Operator: triage alerts (ack/close)
- Commander: escalate + view all

## Core Entities
- Asset: a tracked unit/resource with a location
- Event: raw facts (sensor/log/intel report)
- Alert: actionable item derived from events
- User: authenticated identity with a role
- AuditLog: records of who did what

## Data Flow
Ingest (simulated events) → Store (Postgres) → Query (REST) → Stream (WebSocket) → UI (Map + Inbox)

## Security
JWT authentication + backend-enforced RBAC + audit logging.