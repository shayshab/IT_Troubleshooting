# Okta Verify / Authenticator Troubleshooting

Runbook for enrollment, factor resets, device migrations, and push issues.

## Enrollment & Migration

| Issue | Actions |
|------|---------|
| Cannot enroll | Check MFA enrollment policy for the user. Confirm device time, network, and camera (for QR). Use activation link if QR fails. |
| New phone migration | Add new factor first, then remove old. Use admin‑initiated reset of factors if locked out. Provide backup codes. |

## Push & OTP

| Issue | Actions |
|------|---------|
| No push notifications | Ensure notifications enabled; allow background refresh and battery optimization off. Test cellular vs Wi‑Fi. Fallback to OTP. |
| OTP invalid | Verify time sync on device. Re‑enroll factor if drifted. |

## Admin Tasks

| Task | Actions |
|------|---------|
| Reset factors | Admin Console → Users → select user → Reset Multifactor. Communicate backup sign‑in methods. |
| Policy updates | Adjust MFA policies for step‑up, device binding, and phishing‑resistant methods where possible (WebAuthn). |

## Verification & Handover

- Capture user, device model/OS, app version, timestamps. Attach Okta System Log entries for challenges and pushes when escalating.

