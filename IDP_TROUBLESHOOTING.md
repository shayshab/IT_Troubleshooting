# Identity Provider Troubleshooting (Okta & Entra ID)

Runbook for SSO/SAML/OIDC, MFA, lifecycle, and provisioning.

## Authentication & SSO

| Issue | Actions |
|------|---------|
| SSO fails | Compare clock skew and certificates. Validate ACS/redirect URIs, audience/issuer, and NameID. Check app assignment and user/group mapping. Use logs: Okta System Log; Entra Sign‑in logs. |
| MFA problems | Reset factors; verify policy and enrollments. Confirm push delivery and network reachability to notification services. |

## Provisioning & Lifecycle

| Issue | Actions |
|------|---------|
| SCIM not provisioning | Check SCIM endpoint health, token, and mappings. Review profile push and attribute transforms. |
| Group/role not applied | Verify group membership source (HRIS → IdP → App). Re-run imports and push now. |

## Access Policies

| Task | Actions |
|------|---------|
| Conditional Access / Sign‑on | Review policy order and scope. Test with a pilot user. Examine device compliance claims and CA debug logs. |

## Federation & Apps

| Issue | Actions |
|------|---------|
| OIDC failures | Check redirect URIs, client secret validity, and scope consent. Examine ID token claims and clock skew. |
| SAML attribute mismatch | Align attribute statements with application expectations; test with sample assertion. |

## Verification & Handover

- Capture request IDs, timestamps, user UPN/email, app ID, and geolocation.
- Attach sign‑in logs, policy screenshots, and token/assertion samples when escalating.

