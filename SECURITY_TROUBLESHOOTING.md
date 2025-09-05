# Security Troubleshooting Guide

Senior runbook for malware, phishing, access issues, and incident response.

## Malware & Threats

| Issue | Actions |
|------|---------|
| Suspected malware | Isolate device from network. Run full antivirus scan. Check Windows Defender logs. Use Malwarebytes for additional scan. |
| Ransomware | Disconnect from network immediately. Do not pay ransom. Restore from clean backups. Check for lateral movement. |

## Phishing & Social Engineering

| Issue | Actions |
|------|---------|
| Phishing email | Report to security team. Check email headers and sender reputation. Block sender domain if confirmed malicious. |
| Compromised account | Reset password immediately. Check for unauthorized access. Review sign-in logs. Enable MFA if not already. |

## Access & Permissions

| Issue | Actions |
|------|---------|
| Unauthorized access | Review access logs. Revoke suspicious sessions. Check for privilege escalation. Update access policies. |
| Suspicious activity | Monitor user behavior. Check for unusual login times/locations. Review file access patterns. |

## Endpoint Security

| Issue | Actions |
|------|---------|
| Antivirus not working | Check service status. Update definitions. Reinstall if necessary. Verify real-time protection is enabled. |
| Firewall issues | Check Windows Firewall rules. Verify third-party firewall configuration. Test network connectivity. |

## Incident Response

| Task | Actions |
|------|---------|
| Containment | Isolate affected systems. Preserve evidence. Document timeline. Notify stakeholders. |
| Investigation | Collect logs. Analyze attack vectors. Determine scope of compromise. |

## Verification & Logging

- Use Windows Event Logs for security events.
- Check antivirus console for threat detection.
- Monitor network traffic for anomalies.
- Document all actions taken for compliance.
