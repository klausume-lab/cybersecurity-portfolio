# Journal Entry 4 — File Hash Review

Date: October 12, 2026
Entry: 4
Description
I investigated a suspicious SHA-256 file hash from a phishing incident training scenario using VirusTotal. I reviewed vendor detections, file properties, related names, and the file's likely malware classification. This activity helped me understand how security analysts use threat intelligence to decide whether an alert represents a genuine risk. The work fits the Detection and Analysis phase of the NIST incident response lifecycle.
Tool(s) used
I used VirusTotal to search an existing SHA-256 hash rather than uploading the file. VirusTotal compares the hash against vendor detections and displays static file details. The report showed 52 of 71 security vendors flagged this executable as malicious. I reviewed the Details and Detection tabs, including the MD5 hash and the unsigned Windows executable's filename. The tool supported the assessment, but did not establish the attacker’s identity or the full extent of compromise.
The 5 W's
Who: An unidentified attacker delivered the malicious attachment; the specific threat actor was not verified.
What: A password-protected spreadsheet attachment was opened, triggering a malicious payload. The scenario reports unauthorized executable files appearing on the employee's computer.
When: The employee received the email at 1:11 p.m., opened the attachment at 1:13 p.m., unauthorized files appeared at 1:15 p.m., and the SOC received an IDS alert at 1:20 p.m. The scenario does not provide the calendar date.
Where: An employee's computer at a financial-services organization described in the training scenario.
Why: The file was distributed through a phishing email to induce execution. The attacker's ultimate purpose was not independently determined.
Additional notes
SHA-256: 54e6ea47eb04634d3e87fd7787e2136ccfbcc80ade34f246a12cf93bab527f6b. MD5: 287d612e29b71c90aa54947313810a25. VirusTotal's popular threat label was trojan.flagpro/fragtor. An unsigned file using the name bfsvc.exe and Microsoft utility metadata warrants scrutiny. A response team should isolate and investigate affected devices, retain evidence, and validate associated network indicators before blocking them. No actual production system was accessed during this course exercise.

## Evidence limit

The Drive entry records a VirusTotal lookup on October 12 and 52/71 detections. The historical lookup was not independently rerun during portfolio preparation, and no screenshot is included here. Detection ratios and labels can change. This records a course learning activity, not production incident response.

[Journal index](README.md)
