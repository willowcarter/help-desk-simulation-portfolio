# Windows System Clock & Time Zone Correction (INC0012865)

- **Priority**: High
- **User**: Kevin Park (`kpark@servicedesk-simulator.com`)
- **Department**: Sales (Floor 2)
- **Business Impact**: Incorrect time zone and clock synchronization caused meetings to appear at incorrect times and resulted in a missed meeting.

## Issue Description

The user reported that the clock on his workstation was incorrect. The computer was configured for Eastern Time even though the user was located in Central Time. The system clock was also approximately two minutes behind the correct time.

The incorrect time zone was causing Teams meetings to appear at the wrong times.

![Original incident ticket](images/INC0012865-01-clock-incorrect-ticket.png)

## Root Cause & Diagnosis

The workstation had an incorrect Windows time zone configuration, and the system clock was approximately two minutes out of synchronization.

The user had already restarted the workstation without resolving the issue. I connected to the workstation through a remote support session and reviewed the Windows **Date & Time** settings.

## Resolution Steps

1. Connected to the user's workstation using remote support.

![Remote support session](images/INC0012865-02-remote-support.png)

2. Opened **Windows Settings → Time & Language → Date & Time**.
3. Changed the workstation's time zone from Eastern Time to **Central Time (UTC-06:00)**.
4. Resynchronized the system clock with the configured Internet time server to correct the approximately two-minute time difference.

![Clock synchronized successfully](images/INC0012865-03-sync-clock-complete.png)

5. Asked the user to verify the corrected time and meeting schedule from his workstation.

## Verification

The workstation successfully synchronized its clock after the time zone was corrected. The user confirmed that the clock was displaying the correct time and that the issue was resolved.

![User confirmation](images/INC0012865-04-communication-and-confirmation.png)

## Key Lessons Learned

- Verify the system time zone before investigating more complex hardware or BIOS-related causes.
- Small system-time discrepancies can affect scheduling and user productivity.
- Remote support allows time and system configuration issues to be resolved without requiring physical access to the workstation.

## Skills Demonstrated

- Remote desktop support
- Windows system configuration
- Time zone configuration
- System time synchronization
- End-user communication
- Troubleshooting and verification
