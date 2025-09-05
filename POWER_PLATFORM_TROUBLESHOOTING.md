# Power Platform Troubleshooting Guide

Senior runbook for Power Apps, Power BI, Power Automate, and Power Virtual Agents.

## Power Apps

| Issue | Actions |
|------|---------|
| App not loading | Check app permissions in Power Apps admin center. Verify data source connections and authentication. Review app sharing settings. |
| Data source connection fails | Verify data source permissions and authentication. Check connection references in app settings. Test connection in Power Platform admin center. |
| App performance issues | Review app formulas and data sources. Check for inefficient queries and large data sets. Use app checker for performance recommendations. |

## Power BI

| Issue | Actions |
|------|---------|
| Report not loading | Check workspace permissions and data source access. Verify report sharing settings. Review data refresh status and schedules. |
| Data refresh fails | Check data source credentials and permissions. Verify gateway status if using on-premises data. Review refresh history for error details. |
| Dashboard not updating | Check tile refresh settings and data source connections. Verify user permissions and sharing settings. |

## Power Automate

| Issue | Actions |
|------|---------|
| Flow not running | Check flow run history for error details. Verify trigger conditions and data connections. Review flow permissions and sharing settings. |
| Flow runs but fails | Review error messages in run history. Check data validation and business logic. Verify all required permissions are granted. |
| Flow performance issues | Review flow logic and data operations. Check for unnecessary loops and complex expressions. Use flow checker for optimization suggestions. |

## Power Virtual Agents

| Issue | Actions |
|------|---------|
| Bot not responding | Check bot configuration and topic settings. Verify authentication and permissions. Review conversation logs for errors. |
| Bot deployment issues | Check bot publishing settings and channels. Verify environment permissions and configuration. |

## Environment Management

| Issue | Actions |
|------|---------|
| Environment access issues | Check environment permissions in Power Platform admin center. Verify user roles and security groups. |
| Environment capacity issues | Monitor environment storage and API usage. Review data loss prevention policies. Consider environment cleanup or expansion. |

## Data Loss Prevention (DLP)

| Issue | Actions |
|------|---------|
| DLP policy blocking app | Review DLP policy configuration and data classifications. Add appropriate business justification or adjust policy rules. |
| Data source not allowed | Check DLP policy data source restrictions. Verify data source classification and business justification requirements. |

## Admin Tasks

| Task | Actions |
|------|---------|
| User provisioning | Assign appropriate Power Platform licenses and environment access. Configure security roles and permissions. |
| Environment governance | Set up data loss prevention policies. Configure environment security and sharing settings. Monitor usage and capacity. |

## Verification & Logging

- Use Power Platform admin center for environment health and usage analytics.
- Check Power Platform audit logs for user activities and policy violations.
- Monitor service health dashboard for Power Platform service issues.
