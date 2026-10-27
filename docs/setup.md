# Environment Setup

## 1. Microsoft Entra ID

- Created a personal Microsoft Entra ID Free tenant with Global Administrator access.
- Configured a separate tenant to maintain full control over the lab.
- Added and verified `ad.mustafahasnain.com` using a Cloudflare DNS TXT record.


## 2. On-Premises Active Directory

Using my existing Windows Server 2025 Active Directory environment (`homelab.com`):

- Verified domain controller DNS health using `dcdiag /test:DNS /v`.
- Audited existing users and UPNs using PowerShell.
- Confirmed all users had the `@homelab.com` suffix.


## 3. Hybrid Identity Preparation

Since `homelab.com` is an internal domain I don't own publicly, I configured a verified UPN suffix for cloud authentication.

- **Internal AD domain:** `homelab.com`
- **Cloud UPN suffix:** `ad.mustafahasnain.com`
- Added the alternative UPN suffix through Active Directory Domains and Trusts.
- Kept the existing AD domain unchanged.


## Next Steps

Configure test users, deploy Microsoft Entra Connect Sync, and validate hybrid identity synchronization.
