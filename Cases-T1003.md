Title: Lab-Process create on DESKTOP-IL14NGD
Severity: High
Status: Resolved - True Positive, Authorized Test.
Tags: T1003, Lab-Test

Summery: On 30 September 2026 at 14:27 UTC, User Employee1 On DESKTOP-IL14NGD started mimikatz.exe from powershell. Wazuh rule 100003, Level 12 Matched OriginalFileName and tagged T1003.

Ovservables
-hostname: DESKTOP-IL14NGD
-user: Employee1
-image: C:\Tools\Labs\mimikatz-master\x64\mimikatz.exe (PID: 8240)
-parent: C:\system\win32\WindowsPowershell\v1.0\powershell.exe (PID: 10948)
-SHA256: 61C0810A23580CF492A6BA4F7654566108331E7A4134C968C2D6A05261B2D8A1

Enrichment: Virus Total returned a file report for that SHA256 with a Malicious Count 16 and a Reputation score -118.

Ruled Out: Event 10 / rule Id 100012 was powershell openning a handel for mimikatz.exe not a process opening lsass.exe

Call: Authorized lab test, No Containment, Closed.
