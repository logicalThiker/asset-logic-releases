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

