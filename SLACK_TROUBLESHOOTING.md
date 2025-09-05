# Slack Troubleshooting Guide

Admin-level steps for org settings, SSO, integrations, and call quality.

## Access & SSO

| Issue | Actions |
|------|---------|
| Can't log in | Check `status.slack.com`. If SSO: verify IdP attributes (email, groups), Slack SSO configuration, and user provisioning. Review Audit Logs API for failures. Clear cache or use web vs desktop. |
| Workspace switching issues | Sign out everywhere, remove app cache. Confirm user has membership in target workspace/org. |

## Messaging & Files

| Issue | Actions |
|------|---------|
| Messages not sending | Check connectivity, proxy settings, and firewall. Verify Slack ports/domains are allowed. Test web client. |
| File upload fails | Validate file size and workspace storage. Check DLP or retention rules that may block uploads. |
| Search not working | Rebuild index by logging out/in; verify workspace retention and search scope. |

## Notifications

| Issue | Actions |
|------|---------|
| Notifications missing | Check per‑channel overrides, Do Not Disturb, OS notifications, and Focus modes. On macOS, ensure Slack is allowed in System Settings → Notifications. |

## Calls & Huddles

| Issue | Actions |
|------|---------|
| AV issues | Test mic/camera permissions at OS level. Use Slack network test `https://slack.com/help/test`. Check proxy/firewall for WebRTC (UDP 3478–3481). Gather call logs and console output. |

## Apps, Bots, and Integrations

| Issue | Actions |
|------|---------|
| App not working | Reauthorize app; check scopes, tokens, and event subscriptions. Verify that the app is approved in Org settings. Inspect Audit Logs for denied scopes. |
| Workflow issues | Check Workflow Builder permissions, channel access, and connection to external services. |

## Admin & Security

| Task | Actions |
|------|---------|
| Manage users | Admin → Manage members, roles, SCIM provisioning if enterprise. |
| Retention & Compliance | Verify retention policies and legal holds. Export settings based on plan. |
| Security | Enforce SSO, MFA, and app approval workflows. Review Audit Logs regularly. |

## Verification & Logging

- Capture timestamps, channel IDs, and user IDs.
- Use Slack status page and network test. Save HAR logs for web issues.