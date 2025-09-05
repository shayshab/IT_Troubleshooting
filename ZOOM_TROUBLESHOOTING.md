# Zoom Troubleshooting Guide

Runbook for meetings/webinars, audio/video devices, and account policies.

## Access & Account

| Issue | Actions |
|------|---------|
| Can't sign in | Check `status.zoom.us`. If SSO: verify IdP assignment and Zoom domain claim. Confirm license (Basic/Pro) and feature eligibility. |

## Meetings & Webinars

| Issue | Actions |
|------|---------|
| Join/connectivity issues | Test Zoom network `https://zoom.us/test`. Allow Zoom domains/ports through firewall/proxy. Switch data center regions if restricted. |
| Host/participant permissions | Review meeting settings: waiting room, authentication profiles, and passcodes. For webinars, panelist vs attendee roles. |

## Audio/Video Devices

| Issue | Actions |
|------|---------|
| No mic/camera | OS privacy permissions. Close conflicting apps. Select correct device in Zoom. Update drivers. |
| Echo/feedback | Use one audio device per room, enable suppress background noise, and prefer headsets. |

## Recording & Storage

| Issue | Actions |
|------|---------|
| Cloud recording not available | Check license and admin toggles. Storage quotas and retention policies. |
| Local recording fails | Verify disk space and file permissions. |

## Admin & Security

| Task | Actions |
|------|---------|
| Enforce policies | Admin → Account Settings: SSO, passcodes, waiting room, cloud recording controls. |
| Reporting | Dashboards for call quality, participant metrics, and latency. Export reports for audits. |

## Verification & Logging

- Collect meeting ID, user email, timestamps, client version, and OS.
- Use Zoom support logs and admin dashboards for QoS metrics.

