## v1.3.0

One-click 'Apply Update' now genuinely applies database migrations too, not just code - migrate is now a real, versioned, Watchtower-managed image (with a real code-level safety net in api/gateway so they never serve traffic against a stale schema). No more manual server access needed for a release that adds a migration.

## v1.2.0

General network discovery: find plain workstations/servers on a scanned subnet (not just SNMP infrastructure), automatic recognition of already-managed devices, Guest/Unauthorized/Known classification, one-click Deploy agent from discovery results.

## v1.1.0

Real one-click "Apply Update" (Watchtower-based, images now pulled from ghcr.io/logicalthiker instead of tarball-only); new console Dashboard landing page + grouped top nav; fixed a real on-prem packaging gap (missing CORS_ALLOWED_ORIGIN broke signup/login on every fresh deployment); renamed the confusing "Licenses" button to "Software Licenses"; fixed a real agent bug where a slow inventory cycle could starve heartbeats and make a connected device appear offline (agent v0.3.3).

## v1.0.0

First real server release with the release-check mechanism itself, plus reusable enrollment keys and download-from-portal agent installers.

