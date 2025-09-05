# Troubleshooting Guide

This guide reflects a mature, operations-ready approach to IT support. It adds triage discipline, impact/severity assessment, standard runbooks, and clear escalation paths. Use it to resolve issues efficiently and consistently while capturing the right diagnostics for follow‑up.

---

## Triage & Severity

- Critical (P1): Outage for multiple users or business-critical service. Immediate bridge, engage vendor if applicable, update stakeholders every 15–30 minutes.
- High (P2): Single user blocked or degraded performance impacting a team. Start within 15 minutes, updates every 60 minutes.
- Medium (P3): Workaround available; proceed during business hours.
- Low (P4): Cosmetic or minor inconvenience; schedule.

Always capture: user, device/OS, exact timestamp, network (SSID, IP), screenshots/error codes, scope (one user vs many), and most recent change.

---

## Standard Troubleshooting Flow

1) Identify scope: One user, one segment (e.g., office floor), or org-wide?
2) Reproduce and gather evidence: exact error text, logs, timestamps.
3) Isolate layers: account/identity → application → device → network.
4) Try safe remediations first: cache reset, relogin, toggle service, reboot.
5) Check status pages and admin dashboards for known incidents.
6) Apply targeted fix; verify resolution with the user.
7) Document root cause (if known), actions taken, and prevention steps.

---

## Table of Contents
1. [Mac Troubleshooting](#mac-troubleshooting)
2. [Google Workspace Troubleshooting](#google-workspace-troubleshooting)
3. [Notion Troubleshooting](#notion-troubleshooting)
4. [Slack Troubleshooting](#slack-troubleshooting)
5. [Onboarding & Offboarding Troubleshooting](#onboarding--offboarding-troubleshooting)
6. [WiFi & Router Troubleshooting](#wifi--router-troubleshooting)
7. [Windows Troubleshooting](#windows-troubleshooting)
8. [VPN Troubleshooting](#vpn-troubleshooting)
9. [MDM Troubleshooting](#mdm-troubleshooting)
10. [Identity Provider Troubleshooting](#identity-provider-troubleshooting)
11. [Zoom Troubleshooting](#zoom-troubleshooting)
12. [Jira & Confluence Troubleshooting](#jira--confluence-troubleshooting)
13. [Okta Verify Troubleshooting](#okta-verify-troubleshooting)
14. [Incident Response Playbook](#incident-response-playbook)

---

## Mac Troubleshooting

| Issue | Solution |
|-------|----------|
| Mac won't turn on | Check power, reset SMC, try safe mode |
| Spinning beach ball (slow) | Force quit apps, check Activity Monitor, restart |
| WiFi not connecting | Restart WiFi, forget/rejoin network, reset PRAM |
| Bluetooth not working | Toggle Bluetooth, remove/re-pair devices, reset Bluetooth module |
| App won't launch/crashes | Update/reinstall app, check permissions, restart Mac |
| No sound | Check volume, output device, restart coreaudio |
| External display not detected | Check cables, detect displays, restart Mac |
| Battery draining quickly | Check battery health, close background apps, update macOS |
| Mac overheating | Clean vents, check Activity Monitor, reset SMC |
| Can't install updates | Check storage, safe mode, reset NVRAM |
| Startup disk full | Delete unused files, empty trash, use storage management |
| Time Machine backup fails | Check disk, reconnect drive, restart backup |
| Printer not working | Re-add printer, reset printing system, update drivers |
| Can't connect to VPN | Check credentials, update VPN client, restart network |
| Kernel panic (unexpected restart) | Check for hardware issues, update software, run diagnostics |
| USB devices not recognized | Try different port, check System Information, reset SMC |
| File permissions issues | Use Disk Utility First Aid, repair permissions |
| iCloud sync issues | Sign out/in, check storage, restart Mac |
| Login items causing problems | Remove unnecessary login items, safe mode |
| Screen flickering | Update macOS, reset NVRAM, check display settings |

---

## Google Workspace Troubleshooting

| Issue | Solution |
|-------|----------|
| User can't log in | Reset password, check 2FA, verify account status |
| Email not sending/receiving | Check spam, verify MX records, check quotas |
| Shared Drive access issues | Check permissions, share settings, group membership |
| Google Meet not working | Check camera/mic permissions, browser compatibility |
| Calendar events not syncing | Check sync settings, clear cache, re-add account |
| Drive file not syncing | Restart Drive, check storage, reinstall Drive app |
| Account suspended | Unsuspend in Admin Console, check for policy violations |
| 2-step verification problems | Provide backup codes, reset 2FA |
| Email forwarding not working | Check filters, verify forwarding address |
| Group email issues | Check group settings, member permissions |
| Google Chat not loading | Clear browser cache, check service status |
| Document sharing issues | Check link settings, permissions, domain restrictions |
| Mobile device sync issues | Re-add account, check device management settings |
| Google Forms not submitting | Check form settings, quotas, browser compatibility |
| Admin Console access issues | Check admin roles, login credentials |
| App integration problems | Check API access, OAuth permissions |
| User alias not working | Add alias in Admin Console, check DNS |
| Spam or phishing emails | Report to Google, update filters |
| Storage quota exceeded | Delete files, purchase more storage |
| Google Sites not publishing | Check permissions, browser cache |

---

## Notion Troubleshooting

| Issue | Solution |
|-------|----------|
| Can't log in | Reset password, check SSO, clear cache |
| Page not loading | Check internet, clear cache, try different browser |
| Sync issues across devices | Refresh app, log out/in, update app |
| Permissions/sharing issues | Check workspace permissions, invite again |
| Export/import fails | Try smaller exports, check file format |
| Integration not working | Reconnect integration, check API status |
| Slow performance | Reduce page size, archive unused content |
| Lost content | Check page history, restore from trash |
| Mobile app issues | Update app, reinstall, check permissions |
| Notifications not received | Check notification settings, app permissions |

---

## Slack Troubleshooting

| Issue | Solution |
|-------|----------|
| Can't log in | Reset password, check SSO, clear cache |
| Messages not sending/receiving | Check internet, restart app |
| Notifications not working | Check notification settings, OS permissions |
| App crashing | Update/reinstall app, clear cache |
| Integration/bot not working | Reauthorize integration, check permissions |
| File upload fails | Check file size, storage limits |
| Channel access issues | Check channel permissions, invite user |
| Search not working | Reindex app, clear cache |
| Audio/video call issues | Check mic/camera permissions, restart app |
| Workspace switching issues | Log out/in, clear cache |

---

## Onboarding & Offboarding Troubleshooting

| Issue | Solution |
|-------|----------|
| Account not created/removed | Check automation logs, manual creation/removal |
| Device not set up/decommissioned | Verify imaging process, wipe device securely |
| Access not granted/revoked | Check group memberships, permissions |
| Welcome/exit emails not sent | Check email automation, send manually |
| License assignment issues | Check license pool, assign manually |

---

## WiFi & Router Troubleshooting

| Issue | Solution |
|-------|----------|
| No internet connection | Restart router, check cables, ISP status |
| Slow WiFi | Change channel, move closer, reduce interference |
| Frequent disconnects | Update firmware, check for interference |
| Device can't connect | Forget/rejoin network, check MAC filtering |
| IP conflict | Restart devices, set static IP |
| Router login issues | Reset router, check default credentials |
| Guest network not working | Check settings, restart router |
| DNS issues | Change DNS to Google (8.8.8.8), restart router |
| Firmware update fails | Download correct firmware, reset router |
| Port forwarding not working | Check rules, restart router |

---

---

## Windows Troubleshooting

See `WINDOWS_TROUBLESHOOTING.md` for performance, network, login, update, and evidence collection procedures.

---

## VPN Troubleshooting

See `VPN_TROUBLESHOOTING.md` for client/identity checks, tunnel/routing diagnostics, and network/firewall guidance.

---

## MDM Troubleshooting

See `MDM_TROUBLESHOOTING.md` for Intune/Jamf enrollment, compliance, profiles, and app deployment.

---

## Identity Provider Troubleshooting

See `IDP_TROUBLESHOOTING.md` for Okta/Entra ID SSO, MFA, provisioning, and policy checks.

---

## Zoom Troubleshooting

See `ZOOM_TROUBLESHOOTING.md` for meetings/webinars, device issues, and admin policy guidance.

---

## Jira & Confluence Troubleshooting

See `JIRA_CONFLUENCE_TROUBLESHOOTING.md` for Atlassian Cloud access, project/space permissions, automation, and integrations.

---

## Okta Verify Troubleshooting

See `OKTA_VERIFY_TROUBLESHOOTING.md` for enrollment, factor resets, device migrations, and push/OTP issues.

---

## Incident Response Playbook

See `INCIDENT_RESPONSE_PLAYBOOK.md` for severity, roles, comms, phases, and closure.

---

## Active Directory Troubleshooting

See `ACTIVE_DIRECTORY_TROUBLESHOOTING.md` for AD authentication, GPO, DNS, and domain controller health.

---

## Exchange & Outlook Troubleshooting

See `EXCHANGE_OUTLOOK_TROUBLESHOOTING.md` for mail flow, Outlook profiles, and Exchange server issues.

---

## Microsoft Teams Troubleshooting

See `TEAMS_TROUBLESHOOTING.md` for calls, meetings, admin policies, and client issues.

---

## Security Troubleshooting

See `SECURITY_TROUBLESHOOTING.md` for malware, phishing, access issues, and incident response.

---

## Microsoft 365 Troubleshooting

See `M365_TROUBLESHOOTING.md` for admin center, licensing, compliance, and tenant management.

---

## SharePoint Online Troubleshooting

See `SHAREPOINT_TROUBLESHOOTING.md` for sites, permissions, sync, and content management.

---

## Power Platform Troubleshooting

See `POWER_PLATFORM_TROUBLESHOOTING.md` for Power Apps, Power BI, Power Automate, and Power Virtual Agents.

---

## Escalation & Handover

- When to escalate: sustained P1/P2 impact after 30 minutes, permissions or platform limits, or suspected infrastructure/provider issues.
- What to include: summary, scope, timestamps, screenshots, log snippets, remediation tried, and next hypotheses.
- Handover format: issue, impact, owner, current status, next step, ETA, blockers.

## Post‑Incident Hygiene

- Convert recurring fixes into automation or configuration baselines.
- Add monitoring or alerts where manual checks were needed.
- Create a short runbook entry if a new pattern emerges.

For product‑specific depth, see each section above and the linked admin docs.