### 🔐 Active Directory: Password Reset & Account Recovery (INC0012855)

- **Priority**: High
- **User**: Maria Garcia (`mgarcia@servicedesk-simulator.com`)
- **Department**: Engineering (Floor 3)
- **Business Impact**: Lead developer blocked on payment processing module prior to Friday sprint deadline.

#### Issue Description
End-user reported an inability to log into her workstation following a 3-week vacation. The system prompted that her password had expired, but failed to allow a password change directly from the Windows login screen.

#### Root Cause & Diagnosis
- **Root Cause**: Account password expired during extended leave due to domain password expiration policy.
- **Access Issue**: Local workstation was unable to process the self-service password change at the logon screen without an established domain controller trust/VPN connection.

#### Resolution Steps
1. **Identity Verification**: Verified user identity and details in the Directory tool (`mgarcia@servicedesk-simulator.com`).
2. **Account Audit**: Inspected user profile under **Directory → Authentication** to check account state (MFA Status: Enrolled; Password Expired status).
3. **Administrative Reset**: Performed an administrative password reset via the Directory module.
4. **Temporary Credentials & Enforcement**: Issued a temporary password and configured the account to enforce "User must change password at next logon."
5. **Verification**: Confirmed successful domain login and restored access to the development environment.

#### Key Lessons Learned
- **Extended Leave Policy**: Accounts inactive across password policy cycles will trigger forced resets that often require administrator intervention when off-net.
- **Priority Escalation**: High-impact roles (e.g., lead developers on critical deadlines) require rapid identity verification and password remediation to avoid project delays.
