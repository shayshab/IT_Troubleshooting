# VPN Troubleshooting Guide

Enterprise-oriented runbook covering client, identity, tunnel, and network.

## Intake & Scope

- User, device/OS, client version, location (home/office), ISP, and timestamp.
- Split‑tunnel vs full‑tunnel. Resources unreachable (IP/hostnames) and error codes.

## Client & Identity

| Issue | Actions |
|------|---------|
| Auth fails | Check SSO/MFA status, time sync, and account flags. For Azure/Okta, review logs and recent factor changes. Verify certificate validity if cert‑based. |
| Client errors | Reinstall/repair client. Clear cache/profiles. Verify minimum version. |

## Tunnel & Routing

| Issue | Actions |
|------|---------|
| No tunnel | Inspect logs; confirm adapter creation and IP assignment. Reset network stack (per OS). Disable conflicting adapters (e.g., Hyper‑V/VirtualBox) temporarily. |
| Can't reach internal | Check assigned DNS/search suffixes. `traceroute`/`tracert` to target. Verify split‑tunnel routes and ACLs. Test by IP and by FQDN. |
| DNS split‑brain | Ensure internal DNS resolvers are pushed. Test `nslookup host internal.dns` via VPN. |

## Network & Firewall

| Issue | Actions |
|------|---------|
| Blocks by network | Home routers/ISPs may block UDP ports. Switch to TCP/443 profile if available. Verify proxies. |
| Performance | Check MTU: lower if fragmentation suspected. Continuous ping and packet loss analysis. |

## Platform Specific

- macOS: `log show --last 20m --predicate 'process CONTAINS "netext" OR process CONTAINS "neagent"'`.
- Windows: Event Viewer, and `Get-VpnConnection`, `rasdial` logs.

## Verification & Handover

- Post‑fix: confirm tunnel IP, DNS resolution, and access to key resources.
- Attach logs, timestamps, and profile details when escalating to network team.

