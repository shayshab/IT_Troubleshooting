# Jira & Confluence Troubleshooting Guide (Atlassian Cloud)

Admin-grade runbook for access, projects/spaces, automation, and integrations.

## Access & SSO

| Issue | Actions |
|------|---------|
| Can't log in | Check `status.atlassian.com`. Verify user in Atlassian Admin, product access (Jira/Confluence), and groups. If SSO: check IdP assignment and domain claim. |

## Jira

| Area | Actions |
|------|---------|
| Project access | Project settings → People and Roles; check Permission schemes. |
| Workflows and transitions | Validate conditions/validators; review post functions. |
| Automation | Check rule audit logs, scopes, and limits. |
| Notifications | Check Notification scheme and user email preferences. |

## Confluence

| Area | Actions |
|------|---------|
| Space access | Space settings → Permissions. Group membership and anonymous access. |
| Page restrictions | Check page-level restrictions and inherited restrictions. |
| Macros | Validate macro permissions and app status. |

## Integrations & Apps

| Issue | Actions |
|------|---------|
| Marketplace app broken | Check app logs, scopes, and recent updates. Reinstall if necessary. |
| Webhooks | Verify endpoints and secret validation; check delivery logs. |

## Verification & Logging

- Capture issue keys, space keys, org/site URL, user emails, and timestamps.
- Use Atlassian Admin audit logs and Automation rule audits.

