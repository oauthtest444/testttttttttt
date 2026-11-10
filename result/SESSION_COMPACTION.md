# Session Compaction

Last updated: 2026-11-01T05:25:00Z
Target: `https://console.byteplus.com` (authorized routes: `/datarangers`, `/datatester`, `/ark`, `/ai`, `/alb`)
Target hash: `03aef71f1ba65c11c7ba408a0ebd646abc6e8850fd4cf34ff397d9096f808f27`
Status: completed (`result/SCAN_COMPLETE` exists; no pending required work)

## Session summary

This maintenance session added continuity/auth/scope rules and recorded the
completed scan. No new target testing was performed.

## Discovered surface

- Five top-level routes: `/datarangers`, `/datatester`, `/ark`, `/ai`, `/alb`.
- All discovered sub-routes and 48 inventoried APIs.
- Subdomain inventory: `console.byteplus.com` completed.
- Client-side reports under `result/client-side/console.byteplus.com/`;
  server-side report under `result/server-side/console.byteplus.com/`.

## Tested

- Same-origin routes, sub-routes, APIs, and loaded JavaScript for all five
  top-level routes, including cross-tenant checks with two test accounts.
- Confirmed low-impact read-only cross-project IDOR (`VULN-20261031-001`) in
  DataFinder `common_settings`; benign presentation settings only, below the
  notification bar.
- No high-impact IDOR/BAC, XSS execution, or sensitive postMessage impact
  confirmed.
- Unresolved: Ark managed-agent sub-routes were not activated for the test
  accounts; client-side missing-origin listeners and config-driven redirect
  candidates showed no demonstrable impact.

## Pending / next

- No required work remains for the current completed scan.
- If new subdomains, endpoints, or scope are supplied, verify authorization
  before testing and record new discoveries here immediately.
- Do not repeat prior exclusions automatically; verify against `data/` and the
  program scope, or mark `Scope Unverified`.

## Authentication

- Test account A: AccountID `3000823185` (`test-user-123`).
- Test account B: AccountID `3001021825` (`testt456`).
- Cached auth headers belong only in `creds/auth-headers.txt`; never copy
  cookies, tokens, or secrets into this file, reports, or logs.

## Scope decisions

- `console.byteplus.com` is the authorized host for this completed run; only
  its five listed top-level routes were exercised.
- Other `byteplus.com` subdomains are **scope-unverified**, not automatically
  out of scope. Verify program/data authorization before testing and record
  `Scope Unverified` when ambiguous.
- The related-subdomains note is scope input, not blanket authorization for
  every `byteplus.com` subdomain.

## Workflow closeout

- timestamp: 2026-11-01T06:04:54Z
- run_id: 41279118674
- event: workflow_dispatch
- agent_outcome: failure
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-01T06:24:09Z
- run_id: 41280304453
- event: workflow_dispatch
- agent_outcome: failure
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-01T06:35:13Z
- run_id: 41280842601
- event: workflow_dispatch
- agent_outcome: failure
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-01T06:42:17Z
- run_id: 41281582964
- event: workflow_dispatch
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-01T12:56:45Z
- run_id: 41308755977
- event: schedule
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-01T21:38:26Z
- run_id: 41352926285
- event: schedule
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-02T04:01:10Z
- run_id: 41385991620
- event: schedule
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-02T14:37:53Z
- run_id: 41463486923
- event: schedule
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-03T00:25:26Z
- run_id: 41552563473
- event: schedule
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-03T13:31:13Z
- run_id: 41644820056
- event: schedule
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-03T22:49:57Z
- run_id: 41733972862
- event: schedule
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-04T04:35:31Z
- run_id: 41773968515
- event: schedule
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-04T13:42:27Z
- run_id: 41840339563
- event: schedule
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-04T23:08:38Z
- run_id: 41931103390
- event: schedule
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-05T04:51:43Z
- run_id: 41970245973
- event: schedule
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-05T13:54:30Z
- run_id: 42039740329
- event: schedule
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-05T23:12:31Z
- run_id: 42127637948
- event: schedule
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-06T04:50:57Z
- run_id: 42164756790
- event: schedule
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-06T13:40:16Z
- run_id: 42227184132
- event: schedule
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-06T22:40:09Z
- run_id: 42306281160
- event: schedule
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-07T04:20:08Z
- run_id: 42337871047
- event: schedule
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-07T12:21:27Z
- run_id: 42372005823
- event: schedule
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-07T21:23:45Z
- run_id: 42415548686
- event: schedule
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-08T04:01:23Z
- run_id: 42444972467
- event: schedule
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-08T12:40:29Z
- run_id: 42481240974
- event: schedule
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-08T21:37:38Z
- run_id: 42526037310
- event: schedule
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-09T04:18:23Z
- run_id: 42560946738
- event: schedule
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-09T14:59:30Z
- run_id: 42639839763
- event: schedule
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.

## Workflow closeout

- timestamp: 2026-11-10T01:07:15Z
- run_id: 42733251122
- event: schedule
- agent_outcome: skipped
- workflow_status: failure
- note: Agent-created compaction is authoritative; this closeout records how the run ended.
