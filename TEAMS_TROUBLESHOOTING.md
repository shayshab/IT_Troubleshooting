# Microsoft Teams Troubleshooting Guide

Senior runbook for calls, meetings, admin, and device issues.

## Access & Authentication

| Issue | Actions |
|------|---------|
| Can't sign in | Check `status.office.com`. Verify license assignment in M365 Admin. Clear Teams cache: `%appdata%\Microsoft\Teams`. |
| SSO issues | Check Azure AD app registration and permissions. Verify user assignment to Teams app. |

## Calls & Meetings

| Issue | Actions |
|------|---------|
| Audio/video issues | Check device permissions in OS. Test with Teams device diagnostics. Verify network connectivity and bandwidth. |
| Can't join meetings | Check meeting policy settings. Verify external access if needed. Test with different browsers. |
| Recording not working | Verify recording policy and storage location. Check OneDrive/SharePoint permissions. |

## Chat & Channels

| Issue | Actions |
|------|---------|
| Messages not sending | Check network connectivity. Verify Teams service status. Clear cache and restart. |
| Files not uploading | Check file size limits and storage quotas. Verify SharePoint permissions. |

## Admin & Policies

| Task | Actions |
|------|---------|
| User policies | Teams Admin Center → Users → select user → Policies. Check meeting, calling, and messaging policies. |
| App permissions | Teams Admin Center → Teams apps → Manage apps. Review app permissions and policies. |

## Mobile & Desktop

| Issue | Actions |
|------|---------|
| App crashes | Update to latest version. Clear app data/cache. Reinstall if necessary. |
| Notifications not working | Check OS notification settings. Verify Teams notification preferences. |

## Verification & Logging

- Use Teams Admin Center for call quality analytics.
- Check Azure AD sign-in logs for authentication issues.
- Monitor Teams usage reports for capacity planning.
