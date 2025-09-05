# MDM Troubleshooting Guide (Intune & Jamf)

Enterprise runbook for device enrollment, compliance, profiles, and apps.

## Intake

- Platform (iOS/iPadOS, macOS, Windows), ownership (BYOD/COPE), serial/UDID.
- Enrollment method (ADE/ABM, User‑Driven, Company Portal, DEPNotify), timestamp.

## Enrollment

| Issue | Actions |
|------|---------|
| Device not enrolling | Check ABM assignment to MDM server. For Intune, Company Portal logs and `Settings → Access work or school`. For Jamf, verify PreStage enrollment scope and network reachability to Jamf Cloud. |
| MDM profile install fails | Check time/date, TLS inspection/proxies. For macOS, `sudo profiles -P` and `mdmclient` logs. |

## Compliance & Configuration

| Issue | Actions |
|------|---------|
| Non‑compliant | Intune: Device → Compliance policy; view last check‑in. Sync device, review evaluation results. Jamf: Smart Groups criteria and inventory updates. |
| Profile not applied | Validate assignment/scope tags. For Intune, `Device configuration → Profiles → Per‑setting status`. For Jamf, profile logs and `sudo profiles show -type configuration`. |

## Apps & Updates

| Issue | Actions |
|------|---------|
| App not installing | Intune: monitor app install status and return codes. Check VPP licenses and device/user assignment. Jamf: Policy logs, triggers, and distribution points/CDN. |
| OS updates | Intune: Feature/Quality update policies. Jamf: MDM commands, deferrals, and software update logs. |

## macOS Diagnostics

- Force MDM check‑in: `sudo profiles renew -type enrollment` or `sudo jamf policy && sudo jamf recon`.
- Logs: `/var/log/jamf.log`, `log show --predicate 'subsystem == "com.apple.ManagedClient"' --last 30m`.

## Windows Diagnostics (Intune)

- `dsregcmd /status`, `Get-MDMEnrollment` (if available), Company Portal logs.
- Event Viewer: DeviceManagement‑Enterprise‑Diagnostics‑Provider.

## Verification & Handover

- Confirm policy/profile state, last check‑in time, and compliance. Attach logs and device identifiers when escalating.

