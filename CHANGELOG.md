## v1.5.5 (Windows server)

Server 1.5.5 with agent 0.5.16. Domain Deploy (AD): the WMI deploy-credential list now loads when the screen opens (it was empty until the Deploy screen had been visited); relay and credential pickers show only the selected client's items; malformed OU paths (e.g. 'OU-IT' instead of 'OU=IT') are rejected before testing with the bad part named.

## v1.5.4 (Windows server)

Domain Deploy (AD): only ACTIVE computer accounts get the agent - computers with no domain sign-in within the configured window (default 30 days) and disabled accounts are listed as Skipped and never deployed or added to inventory; a computer that signs in again is deployed on the next sync. Connection test shows active/inactive/disabled counts per OU; computers list shows activity, last sign-in and OS. Agent 0.5.15.

## v1.5.3 (Windows server)

Domain Deploy (AD): connection tests and syncs can no longer hang - every LDAP step is time-limited and runs without blocking the relay's other commands; a test with no result now says whether the relay never picked it up or got stuck. Agent 0.5.14.

## v1.5.2 (Windows server)

Domain Deploy (AD): Test connection before linking (bind + every OU checked, per-OU computer counts; nothing syncs or deploys until the test passes), Edit and Remove for linked domains (fixes the remove error), clearer LDAPS hostname guidance. Check for updates in the profile menu; servers now check hourly. Agent 0.5.13.

## v1.5.1 (Windows server)

Fixes: modules added after the original license (Domain Deploy / AD sync, Autonomous Remediation) now show in the console; no more false 'gateway unreachable' banner after an update on Windows servers.

## v1.5.0 (Windows server)

Security hardening: login lockout, 15-minute sessions with automatic renewal and real sign-out, one-time enrollment/credential tokens can't be reused, safer handling of remote command inputs (JIT admin, browser policy, self-service portal, zero-trust relay). Browser policy now keeps existing Group Policy entries. A replaced license file is picked up within a minute. Deploy page shows Active Directory domain deploy. Agent 0.5.11.

## v1.4.9

Fix agent-releases Docker volume (bind mount, not named volume); auto-create default Client at signup; fix .dockerignore build-context bloat; add real Active Directory domain sync; bundle self-hosted AI (Ollama) into docker-compose.

## v1.4.8

v1.4.8: Console redesigned to match the Spark Admin template (dark sidebar, lime accent, new card/table/button/badge system). Apply Update now shows real progress (spinner, live polling) and a post-update health check confirming api/database/gateway are all responding, with a specific warning naming what failed if not. Fixed the version-checker getting stuck for hours after a failed startup attempt - now retries every 2 minutes until it succeeds.

## v1.4.7

v1.4.7: Fix vulnerability false positives (NVD keyword-search matches with no version range now file as Unconfirmed instead of Open forever, retroactive migration included) and add missing delete confirmations across 7 console actions (assets, maintenance log, custom fields, vendors, contracts, branding domain, SSO config, SCIM group mappings).

## v1.4.6

SECURITY: local admin passwords were being stored and displayed in plaintext in the Run Script command history - fixed going forward and retroactively (existing exposed passwords in the database are now scrubbed). Also: device online/offline status is now computed server-side (fixes a real clock-skew bug that silently disabled Wake-on-LAN, Run Script, and on-demand Backup), a Details button on the Devices list, a one-click Add to Asset Register action, a disposed-asset badge fix, and Audit Log filters now support partial matches.

## v1.4.4

Fixed a real stale-session gap (a reopened tab could fail silently for up to an hour) and Billing now shows real license status for on-prem customers instead of a subscription prompt.

## v1.4.3

Asset Register rebuilt to full ICTMIS feature parity: stat cards, filters, a complete add/edit form (~45 fields), and a tabbed detail view (Overview/History/Maintenance/Audit) with assign, physical verification, and lifecycle/operational status tracking.

## v1.4.2

Added opt-in LICENSE_SYNC_URL background license sync: an on-prem server can now automatically pick up license changes from a vendor-controlled URL, with no manual file handoff needed.

## v1.4.1

Fixes a real bug where the 'update available' banner (and its Apply Update button) rendered hidden behind the Dashboard landing page, making it invisible and unclickable for anyone whose console opens to the Dashboard on login.

## v1.4.0

Real IT Asset Management: fleet-wide Patch Management and Software Inventory pages, Vulnerability Assessment promoted to primary navigation, plus a genuinely new Asset Register, Vendor & Contract tracking, and Reuse & Disposal workflow. Also fixes a significant client-side bug where every DELETE action across the whole product silently failed to show as successful even though it had actually worked.

## v1.3.0

One-click 'Apply Update' now genuinely applies database migrations too, not just code - migrate is now a real, versioned, Watchtower-managed image (with a real code-level safety net in api/gateway so they never serve traffic against a stale schema). No more manual server access needed for a release that adds a migration.

## v1.2.0

General network discovery: find plain workstations/servers on a scanned subnet (not just SNMP infrastructure), automatic recognition of already-managed devices, Guest/Unauthorized/Known classification, one-click Deploy agent from discovery results.

## v1.1.0

Real one-click "Apply Update" (Watchtower-based, images now pulled from ghcr.io/logicalthiker instead of tarball-only); new console Dashboard landing page + grouped top nav; fixed a real on-prem packaging gap (missing CORS_ALLOWED_ORIGIN broke signup/login on every fresh deployment); renamed the confusing "Licenses" button to "Software Licenses"; fixed a real agent bug where a slow inventory cycle could starve heartbeats and make a connected device appear offline (agent v0.3.3).

## v1.0.0

First real server release with the release-check mechanism itself, plus reusable enrollment keys and download-from-portal agent installers.

