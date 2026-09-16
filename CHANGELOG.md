## v1.2.0

General network discovery: find plain workstations/servers on a scanned subnet (not just SNMP infrastructure), automatic recognition of already-managed devices, Guest/Unauthorized/Known classification, one-click Deploy agent from discovery results.

## v1.1.0

Real one-click "Apply Update" (Watchtower-based, images now pulled from ghcr.io/logicalthiker instead of tarball-only); new console Dashboard landing page + grouped top nav; fixed a real on-prem packaging gap (missing CORS_ALLOWED_ORIGIN broke signup/login on every fresh deployment); renamed the confusing "Licenses" button to "Software Licenses"; fixed a real agent bug where a slow inventory cycle could starve heartbeats and make a connected device appear offline (agent v0.3.3).

## v1.0.0

First real server release with the release-check mechanism itself, plus reusable enrollment keys and download-from-portal agent installers.

