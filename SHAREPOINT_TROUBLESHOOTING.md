# SharePoint Online Troubleshooting Guide

Senior runbook for sites, permissions, sync, and content management.

## Site Access & Permissions

| Issue | Actions |
|------|---------|
| Can't access site | Check site permissions in SharePoint admin center. Verify user is in correct groups. Check external sharing settings if external user. |
| Permission inheritance broken | Review site permissions and check for custom permission levels. Restore inheritance if needed. Use PowerShell: `Set-SPOSite -Identity <site> -SharingCapability ExternalUserAndGuestSharing` |
| External sharing not working | Check tenant sharing settings in SharePoint admin center. Verify site-level sharing policies. Review DLP policies that may block sharing. |

## OneDrive Sync Issues

| Issue | Actions |
|------|---------|
| Files not syncing | Check OneDrive sync client logs: `%localappdata%\Microsoft\OneDrive\logs`. Reset sync: right-click OneDrive icon → Settings → Reset sync. |
| Sync conflicts | Resolve conflicts in OneDrive folder. Check file permissions and sharing settings. Use SharePoint web interface to resolve conflicts. |
| Large file sync issues | Check file size limits (15GB per file). Verify available storage space. Use SharePoint web interface for very large files. |

## Document Libraries & Lists

| Issue | Actions |
|------|---------|
| Document not opening | Check file permissions and sharing settings. Verify file is not corrupted. Try opening in browser vs desktop app. |
| Version history issues | Check versioning settings in library settings. Verify user has permission to view versions. |
| Metadata not updating | Check column settings and data types. Verify user has edit permissions. Check for calculated columns or workflows. |

## Search & Discovery

| Issue | Actions |
|------|---------|
| Search not finding content | Check search permissions and content sources. Verify content is indexed. Use search center for advanced queries. |
| Content not appearing in search | Check searchable settings in library/list settings. Verify content is published and not in draft. |

## Workflows & Automation

| Issue | Actions |
|------|---------|
| Workflow not running | Check workflow status in library settings. Verify workflow permissions and triggers. Review workflow history for errors. |
| Power Automate flows failing | Check flow run history in Power Automate. Verify permissions and data connections. Review error messages and retry logic. |

## Mobile & Apps

| Issue | Actions |
|------|---------|
| Mobile app issues | Update SharePoint mobile app. Check device permissions and network connectivity. Clear app cache and re-authenticate. |
| Office integration problems | Verify Office apps are updated. Check file associations and default programs. Reinstall Office if necessary. |

## Admin Tasks

| Task | Actions |
|------|---------|
| Site collection management | Use SharePoint admin center to manage site collections, storage quotas, and external sharing policies. |
| Content migration | Use SharePoint Migration Tool or third-party tools for large-scale content migration. Plan for permissions and metadata preservation. |

## Verification & Logging

- Use SharePoint admin center for site usage and storage reports.
- Check Unified Audit Log for user activities and permission changes.
- Monitor OneDrive sync health dashboard for sync issues.
