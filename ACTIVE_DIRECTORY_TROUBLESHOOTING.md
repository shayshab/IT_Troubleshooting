# Active Directory Troubleshooting Guide

Senior runbook for AD, GPO, DNS, and domain controller issues.

## Authentication & Login

| Issue | Actions |
|------|---------|
| Can't log in to domain | Check time sync: `w32tm /query /status`. Verify DNS resolution: `nslookup domain.com`. Test with cached credentials (disconnect network). Check account lockout status in AD Users and Computers. |
| Account locked out | Check Event Log on DCs for source IP. Review failed login attempts. Unlock account and investigate source. |

## Group Policy

| Issue | Actions |
|------|---------|
| GPO not applying | Run `gpresult /r` and `gpupdate /force`. Check GPO scope, security filtering, and WMI filters. Review Event Log → Group Policy. Use Group Policy Modeling. |
| Slow logon | Check GPO processing time in Event Log. Disable unnecessary GPOs. Use loopback processing if needed. |

## DNS Issues

| Issue | Actions |
|------|---------|
| DNS resolution fails | Check forwarders and root hints. Verify zone replication. Test with `nslookup` and `dig`. Check for stale records. |
| Zone replication | Use `repadmin /showrepl` to check replication status. Force replication if needed. |

## Domain Controller Health

| Issue | Actions |
|------|---------|
| DC not responding | Check services: Netlogon, DNS, Kerberos. Verify FSMO roles. Check disk space and Event Log. |
| Replication issues | Use `repadmin /showrepl` and `dcdiag`. Check network connectivity between DCs. |

## Verification & Logging

- Use `dcdiag /v` for comprehensive DC health check.
- Check Event Logs on DCs for errors and warnings.
- Document any FSMO role transfers or DC promotions.
