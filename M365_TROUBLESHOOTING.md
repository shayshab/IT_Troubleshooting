# Microsoft 365 Troubleshooting Guide

Senior runbook for M365 admin center, licensing, compliance, and tenant management.

## Admin Center & Tenant

| Issue | Actions |
|------|---------|
| Can't access admin center | Verify admin role assignment in Azure AD. Check conditional access policies. Use `https://admin.microsoft.com` or `https://admin.partner.microsoft.com` for CSP tenants. |
| Tenant health issues | Check Service Health dashboard in admin center. Review Message Center for planned maintenance. Verify tenant status in Azure AD. |

## Licensing & User Management

| Issue | Actions |
|------|---------|
| License assignment fails | Check available licenses in Billing → Licenses. Verify user eligibility and group membership. Use PowerShell: `Set-MsolUserLicense` for bulk operations. |
| User provisioning issues | Check Azure AD Connect sync status. Verify user source (on-premises vs cloud). Review provisioning logs in Azure AD. |

## Security & Compliance

| Issue | Actions |
|------|---------|
| Security policies not applying | Review Security & Compliance center. Check policy assignments and exclusions. Verify user/group targeting. |
| Data loss prevention alerts | Review DLP policy matches in Security & Compliance. Adjust policy sensitivity or add exceptions. |

## Exchange Online

| Issue | Actions |
|------|---------|
| Mail flow issues | Check Exchange admin center → Mail flow → Rules. Verify connectors and accepted domains. Use Message Trace for troubleshooting. |
| Mailbox permissions | Review mailbox delegation in Exchange admin center. Check sharing policies and external access settings. |

## SharePoint Online

| Issue | Actions |
|------|---------|
| Site access issues | Check site permissions in SharePoint admin center. Verify external sharing settings. Review site collection admin rights. |
| Sync problems | Check OneDrive sync client logs. Verify tenant sync settings. Reset sync if necessary. |

## Teams Administration

| Issue | Actions |
|------|---------|
| Teams policies not applying | Review Teams admin center → Policies. Check user assignments and policy precedence. Use PowerShell for bulk policy updates. |
| Meeting policies | Verify meeting settings and restrictions. Check audio/video policies. Review external access settings. |

## Power Platform

| Issue | Actions |
|------|---------|
| Power Apps not working | Check Power Platform admin center. Verify environment permissions and data loss prevention policies. |
| Power BI access issues | Review Power BI admin portal. Check workspace permissions and sharing settings. |

## Verification & Logging

- Use Microsoft 365 admin center for service health and usage reports.
- Check Azure AD audit logs for authentication and authorization issues.
- Monitor Security & Compliance center for security alerts and compliance reports.
