# Detection 100003 — process create matched on OriginalFileName

Home-lab detection. Isolated Windows VM only. No production systems.

## What I built

Sysmon on a Windows 11 lab VM records process creation. A Wazuh agent ships those events to a Wazuh manager. Custom rule **100003** (level 12) chains off Wazuh’s Sysmon process-create rule and matches `originalFileName` for a known credential-dumping tool, tagged MITRE **T1003**.

Shuffle Cloud receives **only** rule 100003 (not every alert). A regex pulls the SHA256 out of Sysmon’s combined hash string. VirusTotal returns a file report for that hash.

## Why OriginalFileName

The path and the file name can be changed. `OriginalFileName` is a name stored inside the file. A hash still identifies the file if that name is changed too. Name-only rules are lab scaffolding, not the whole detection.

## Close note

On 30 September 2026 at 14:27 UTC, user Employee1 on DESKTOP-IL14NGD started the test binary from PowerShell. Rule 100003, level 12, matched OriginalFileName and tagged T1003. Child PID 8240, parent PID 10948 (`powershell.exe`). A second alert was PowerShell opening a handle to that new process, not a process opening `lsass.exe`. VirusTotal returned a file report for the SHA256. Authorized lab test. True positive, no containment, closed.

## Not in this repo

Webhook URLs, API keys, and VM passwords are not stored here.
