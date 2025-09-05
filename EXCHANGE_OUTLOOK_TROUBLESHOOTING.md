# Exchange & Outlook Troubleshooting Guide

Senior runbook for mail flow, profiles, and client issues.

## Mail Flow

| Issue | Actions |
|------|---------|
| Email not sending/receiving | Check Exchange health dashboard. Verify MX records and SPF/DKIM/DMARC. Test with `Test-MailFlow` cmdlet. Check transport rules and quarantine. |
| External delivery fails | Review message tracking logs. Check IP reputation and throttling. Verify outbound connector configuration. |

## Outlook Client

| Issue | Actions |
|------|---------|
| Profile corruption | Create new profile in Control Panel → Mail. Use `/resetnavpane` switch if needed. |
| Sync issues | Run `Outlook /safe` mode. Check OST file size and recreate if >2GB. Verify Exchange connectivity with `Test-Connectivity`. |
| Slow performance | Disable unnecessary add-ins. Check OST file location and disk space. Use `Outlook /cleanviews` to reset views. |

## Exchange Server

| Issue | Actions |
|------|---------|
| High CPU/Memory | Check `Get-Process` and `Get-ExchangeServer | Get-HealthReport`. Review Event Logs for errors. |
| Database issues | Run `eseutil /mh` on database. Check for corruption and run repair if needed. |

## Mobile Devices

| Issue | Actions |
|------|---------|
| ActiveSync issues | Check device in EAC → Mobile. Reset device partnership. Verify ActiveSync policy settings. |
| Calendar sync | Verify Exchange Web Services. Check device time zone and calendar permissions. |

## Verification & Logging

- Use Exchange Management Shell for detailed diagnostics.
- Check Message Tracking Logs for delivery issues.
- Monitor Exchange health with built-in monitoring tools.
