## v1.8.1 (Windows server)

Choose what the console calls a client: Settings > Branding > "Call clients": Clients (default) or Locations.
- In Locations mode every console label says location (All locations, Add location, reports, pickers, headings), and the asset register's buildings/floors/rooms are called areas.
- The server says the same: error messages, alert emails, SMS, Teams and Slack messages, notification settings, custom-report columns, the inventory CSV heading and the AI assistant.
- Data, API fields and licences are unchanged; organizations that keep Clients see no change.
Agent stays 0.5.39.

## v1.8.0 (Windows server)

Security release (security roadmap 1-14), agent 0.5.39 for Windows, Linux and macOS.
- Security posture checks and score per device and client
- Microsoft Defender management, network isolation, EDR connectors (Defender for Endpoint, SentinelOne, CrowdStrike)
- Security alerts by email, SMS, Teams, Slack; SIEM forwarding (syslog CEF/JSON)
- Console IP allow-list, password re-check before remote sessions, scoped API tokens, agent tamper protection
- Vulnerability matching by product identity (CPE); Linux CVEs from distribution advisories
- CIS Level 1 baseline with fixes; NIST CSF 2.0, CIS v8, CERT-In, DPDP Act frameworks
- BitLocker enforcement (key kept first, resumes after restart)
- Unknown/unauthorized network device alerts and blocking; port, service and CVE scan of network devices
- Fix & Verify: vulnerability -> approved fix -> rescan confirms
- Just-in-time remote access approval; file transfer and clipboard per role
- Linux security parity; first macOS agent
- DLP finds Aadhaar and PAN (also in Word/Excel); Firefox history and extensions
- SaaS and AI-tool allow/block policy enforced in Chrome, Edge and Firefox
- SOC partner hand-off (separate licence module soc-partner)
Fixes: Linux agents no longer self-update with the Windows build; secret-key rotation now covers all encrypted columns.

## v1.7.4 (Windows server)

Agent 0.5.28: patch pushes and scripts you run can take longer than 2 minutes (patch pushes up to 60 minutes, scripts up to 30), and a script stopped at its limit now says so. Duplicate devices: a record whose agent never checked in is merged with the same computer, and all devices are checked for duplicates daily - press 'Merge duplicates now' (Settings > Device Placement) to clean up straight away.

## v1.7.3 (Windows server)

Fleet patching fix: installs now run in the background on each device (no more cut-off installs and 'exit status 1'), each update is tried even if another fails, and results are clearer - 'already up to date' is not a failure, restarts needed are shown, error codes are readable and Windows Update connection problems are named. Re-run any deployment that failed.

## v1.7.2 (Windows server)

AI assistant: ask questions about your devices, updates, vulnerabilities and tickets, and have tasks prepared for you to confirm (patch installs now or scheduled, scans, restart/lock/wake, move device, run script, placement rules, notification recipients, user roles, tickets). Common commands are answered instantly without AI. New setting 'AI stays on this server' keeps all AI on this server; the optional Asset-Logic AI pack (separate download) adds a private, on-server AI.

## v1.7.1 (Windows server)

Fleet patching: Patch Management lists every missing Windows and app update across a client or all clients; tick updates and install them on every device that needs them, now or at a scheduled time, with per-device progress and cancel. Vulnerability Assessment: 'Scan all devices' for a client or the whole organisation, in the background with progress. The navigation menu now opens beside the item clicked.

## v1.7.0 (Windows server)

Device Placement: rules (computer name, IP subnet, AD OU, domain, model, serial and more) move new devices from a common place to the right client and site on their first inventory report, with a preview and 'Run rules now'; devices can be moved between clients by hand. A re-installed or re-imaged machine is merged with its earlier record (history kept), so devices are never listed twice. Notifications: recipients choose events (device placed or unassigned, duplicate merged, hardware change, security alert) by email and/or SMS through Twilio or any HTTP SMS gateway (MSG91, TextLocal, ...), with a test button.

## v1.6.9 (Windows server)

Settings from the console instead of config files: Server Settings (email with test email, TLS mode, sign-up, device key rotation, trusted proxies, remote-desktop relay, NVD/HIBP/AI keys, update window, off-site backups) applied by the server with automatic rollback; Certificates page to install your own TLS certificate (.pfx or PEM) for browsers while agents keep the built-in one; Branding logo upload and a primary/highlight colour theme. Remote desktop: live picture with much lower delay through the gateway, and the page layout is restored after a session ends.

## v1.6.8 (Windows server)

Security hardening before the VAPT (another organisation's records answer 404; logout ends the session at once; stronger passwords; stricter console security headers) and the redesigned console: navigation rail with Ctrl+K search, device list with saved views and bulk actions, device health scores, a new home screen, device page summary with fixes, and a unified inbox.

## v1.6.7 (Windows server)

Fixes server updates failing (exit 5 / rollback did not complete): the gateway crashed when its service was stopped, Windows restarted it and it locked its own files during the update. Setup now also handles the older gateway safely.

## v1.6.6 (Windows server)

1.6.6: licences update themselves - the server picks up a re-issued licence from the vendor automatically (no file to replace), and an all-modules licence covers modules added later; only strong TLS ciphers (AES-GCM/ChaCha20) and no HTTP TRACE on every port (pre-VAPT hardening). Agent 0.5.27 unchanged.

## v1.6.5 (Windows server)

1.6.5: the server's services run as native Windows services (NSSM removed); the secret-encryption key can be changed with setup -RotateSecretKey; licences accept rotated vendor keys; a signed agent setup stays signed with its download settings; the device Backup tab refreshes running backups; the update notice only offers newer versions. Agent 0.5.27 unchanged.

## v1.6.4 (Windows server)

1.6.4: fixes 1.6.3, where the API refused requests passed on by the new single agent port (8443), so the console and agent update checks failed and the update rolled back. Agent 0.5.27 unchanged.

## v1.6.3 (Windows server)

1.6.3: agents need only one public port (8443); portal agent download is now a normal Windows setup wizard and tries the private then public address; security fixes (Batches 8-11: security alerts and incident register, per-organisation AI setting, credential rotation, enrolment and session hardening, supply-chain controls). Agent 0.5.27.

## v1.6.2 (Windows server)

The 'Confirm it's you' box now opens in the remote desktop window instead of behind it. Server addresses saved in the console are added to the server certificate automatically (no need to re-run setup).

## v1.6.1 (Windows server)

Fixes agents that went offline after moving to encrypted connections in 1.6.0 (they reconnect by themselves after this update; agent 0.5.26). Adds encrypted nightly backups with a recovery key and weekly restore tests, two-factor sign-in (required for Owners and Admins by default) with confirmation before sensitive actions, emailed password reset, safer session storage, SSO domain proof and account linking, per-service accounts and tighter firewall rules, and security updates (Go 1.26.9).

## v1.6.0 (Windows server)

Security and compliance release (ISO 27001 / GDPR remediation), plus editable server addresses.

- Encrypted connections: new installs are TLS-only; upgrades run plain and TLS side by side (new ports 8443/8444/9443/9444) and agents move to TLS by themselves.
- Server Addresses (Organization menu): set a private and a public address; agents try the private one first and fall back to the public one. No reinstall needed.
- Agent 0.5.25: signed updates only, locked-down agent folders, server certificate pinning, private/public address fallback.
- Accounts: new and reset users must change their password; login lockout per email and IP; site-level access enforced across all data; SCIM can't remove Owners.
- Audit log is append-only with a tamper-evident hash chain; file transfers and commands are audited.
- Device erase, data retention and per-user data export (GDPR).
- Backups and session recordings are encrypted at rest.
- DLP scanning is now opt-in.
- HTTP hardening: request size limits, timeouts, security headers, console Content-Security-Policy, outbound request guard.

## v1.5.14 (Windows server)

Remote desktop overhaul (agent 0.5.21): sharp capture on scaled laptop displays, visible remote cursor, faster/lighter streaming, UAC prompts and lock screen visible, Ctrl+Alt+Del and Send keys menu, full screen, H.264 video on direct connections, recordings play at correct speed.

## v1.5.13 (Windows server)

Remote desktop: eliminates minutes-behind lag by dropping stale frames on slow links (agent 0.5.20). Clicks/cursor now track correctly once a device updates to 0.5.20.

## v1.5.12 (Windows server)

Remote support: clicks now land precisely, including on multi-monitor machines (agent 0.5.19). Earlier fixes (letterbox click mapping, normal cursor, agent download) carry forward.

## v1.5.11 (Windows server)

Remote support: clicks now land correctly on a letterboxed remote screen, and the pointer is the normal arrow instead of a crosshair. Console: open panels no longer let the page behind show through the top bar.

## v1.5.10 (Windows server)

Fixes agent downloads returning 404 on native servers: the version-less agent name now serves the current release, so relay, Group Policy and Intune installs work again.

## v1.5.9 (Windows server)

Deploy installer reports failures from the target computer; device action history paged (10 per page) with search and status filter; search and paging on every console list; AD Domain Deploy 'Install now' for chosen computers.

## v1.5.8 (Windows server)

Agent install without WinRM: relay push now falls back from WinRM to WMI over DCOM to Task Scheduler over SMB; new Group Policy install option for domains (startup script, no inbound ports or admin credential needed).

## v1.5.7 (Windows server)

Domain Deploy fix: computers no longer stuck at Deploy Queued - real deploy status tracking, no duplicate re-queuing, batched deploys (5 at a time, follow-up sync every 10 min), stale backlog cleared on upgrade, live status and failure reason per computer; agent 0.5.18 runs scripts without blocking syncs and connection tests.

## v1.5.6 (Windows server)

Cloud Directory connector (Microsoft Entra ID device discovery + optional Intune agent deployment); Domain connection test limited to 1 minute with a Stop test button; agent 0.5.17 (shorter LDAP timeouts).

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

