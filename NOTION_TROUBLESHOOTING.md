# Notion Troubleshooting Guide

Admin-focused guidance for workspaces, permissions, and data recovery.

## Access & Authentication

| Issue | Actions |
|------|---------|
| Can't log in | Check `status.notion.so`. For SSO/SAML: verify IdP attributes (email, groups) and Notion domain claim. Confirm user invitation and seat availability. Clear cache or try desktop app vs browser. |
| SSO loop or denied | Validate ACS/Entity IDs, certificate validity, and user provisioning method (Just‑in‑Time vs manual). Review IdP logs and Notion audit for sign‑in attempts. |

## Pages, Permissions, and Sharing

| Issue | Actions |
|------|---------|
| Page not loading | Try different browser/profile. Disable extensions. Check large databases for heavy filters or rollups; simplify views. |
| Permissions issues | Open Share dialog → verify direct members, groups, and workspace access. For guests, confirm external sharing policy in Workspace Settings. Use Access analytics to trace who can view. |
| Lost content | Page History → Restore previous version. Check Trash for deleted pages. For databases, check individual item history. |

## Sync and Performance

| Issue | Actions |
|------|---------|
| Device sync issues | Log out/in on all devices. Update app. Confirm single account in use. Reduce offline cache by reinstalling. |
| Slow performance | Split mega pages into subpages. Limit rollups/formulas, and hide heavy relations in default views. Use lightweight views for daily use. |

## Integrations & API

| Issue | Actions |
|------|---------|
| Integration failing | Notion Settings → Connections: check installed integration and its scopes (databases:read/write). Reconnect token. Verify database is shared with the integration. Review API responses and rate limits. |

## Workspace Admin

| Task | Actions |
|------|---------|
| Manage members | Workspace Settings → Members: verify roles (Member vs Admin), group assignments, and guests. |
| Security | Enforce SSO, 2FA, and domain restrictions. Disable public page sharing if required. |
| Backups | Schedule periodic exports (Markdown/CSV) for key spaces. Maintain admin break‑glass account. |

## Verification & Logging

- Capture timestamps and URLs when errors occur.
- Use Notion status page and in‑app analytics.
- Maintain a minimal repro page for recurring issues.