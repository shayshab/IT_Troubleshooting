# Google Workspace Troubleshooting Guide

Use these admin-grade steps with clear console paths and verification.

## Identity & Access

| Issue | Actions |
|------|---------|
| User can't log in | Admin Console → Users → select user: check status (Active/Suspended), reset password, verify 2‑Step status. Check SSO logs under Reports → Audit → Login. If SSO: IdP logs and recent password/attribute changes. |
| 2‑Step verification issues | Generate backup codes; temporarily disable enforcement via Admin Console → Security → 2‑step Verification. Confirm recovery options set. |
| Admin Console access denied | Admin Console → Directory → Admin roles: confirm role and scope. Check Context-Aware Access if enabled. |

## Gmail / DNS / Delivery

| Issue | Actions |
|------|---------|
| Email not sending/receiving | Check `workspace.google.com/status` for Gmail. Admin Console → Apps → Google Workspace → Gmail → Troubleshooting: trace message. Verify MX via `dig MX yourdomain.com +short` should point to Google. SPF: `dig TXT yourdomain.com +short` contains `include:_spf.google.com`. DKIM: Admin Console → Gmail → Authenticate email; confirm selector publishes `google._domainkey`. DMARC: `dig TXT _dmarc.yourdomain.com +short`. Check quotas and sender limits. |
| Forwarding not working | User Settings → See Filters and Forwarding; confirm verification. Check Admin Console → Gmail routing rules that may override. |
| Spam/phishing | Review Postmaster Tools. Tighten inbound/outbound content compliance and spoofing protection. Educate users and add report phishing shortcut. |

## Drive / Shared Drives

| Issue | Actions |
|------|---------|
| File not syncing / Drive for desktop | Confirm storage available. Reboot Drive app. Admin Console → Apps → Drive and Docs → Features and Applications: confirm Drive for desktop allowed. Check `~/Library/Application Support/Google/DriveFS` logs. |
| Shared Drive access | Check membership and role (Manager/Contributor/Viewer). For external sharing, check Admin Console → Rules → Sharing settings and domain allowlists. |

## Calendar / Meet

| Issue | Actions |
|------|---------|
| Events not syncing | Re-add account on device. Check Calendar Interop if using Exchange. Verify calendar visibility and sharing. |
| Meet camera/mic issues | Browser permissions, OS privacy permissions. Test at `https://meet.google.com/check`. Check Admin Console → Apps → Google Workspace → Google Meet settings and service status. |

## Groups / Chat / Sites

| Issue | Actions |
|------|---------|
| Group delivery problems | Admin Console → Groups → select group → Members and Settings. Check posting permissions and moderation. Validate group is recognized as Collaborative Inbox if required. |
| Google Chat issues | Clear cache. Admin Console → Apps → Google Workspace → Google Chat settings. Check service status and device management restrictions. |
| Sites not publishing | Confirm site visibility (Anyone with link vs within domain). Check Admin Console → Apps → Additional Google Services → Sites sharing settings. |

## APIs / Integrations

| Issue | Actions |
|------|---------|
| App integration failing | Admin Console → Security → API Controls → App access control. Verify OAuth scopes and trust for domain‑wide delegation. Review audit logs under Reports → Audit for blocked scopes. |

## Security & Compliance

| Issue | Actions |
|------|---------|
| Suspicious login | Reports → Security → Alert Center and Investigation tool. Enforce 2‑Step and Context‑Aware Access. |
| eDiscovery/retention | Google Vault: verify retention rules, holds, and search. |

Reference: use Message Header Analyzer for Gmail and Google Admin Toolbox for diagnostics.