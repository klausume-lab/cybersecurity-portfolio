# Journal Entry 3

Date: October 10, 2026
Entry:
3
Description
I reviewed a suspected phishing alert involving an HR job-application email and a malicious executable attachment. Using the provided playbook, I documented the warning signs and escalated the training ticket for Level 2 review.
Tool(s) used
I used the provided alert ticket, the phishing incident response playbook (including its decision flowchart), and Google Docs. The course states that the file hash was previously verified as malicious; I did not independently run a hash lookup, open the attachment, or examine endpoint logs.
The 5 W's 
* Who: An unidentified sender used the name “Def Communications” in the email header and signed the message “Clyde West.” The real person or group behind it is unknown.
* What: A Medium-severity phishing alert (A-2703) flagged a suspicious job-application email with an executable attachment, bfsvc.exe. The activity says the attachment's SHA-256 hash was already confirmed malicious. I updated the ticket to Escalated for further investigation.
* When: The email was sent Wednesday, July 20, 2022, at 9:30:14 a.m. The alert review date is October 10, 2026; the exact time of any download or execution is not established.
* Where: The email was addressed to the HR inbox at inergy.com in the financial-services company's training scenario. The potentially affected employee device has not been identified in the provided evidence.
* Why: The email presented the attachment as a password-protected resume for an engineering vacancy, apparently to persuade HR to open it. The sender's underlying objective and whether the file executed still require investigation.
Additional notes
My assessment is that the alert should be escalated under Step 3.2 of the phishing playbook. The suspicious sender details, poor wording, and supposed resume arriving as an .exe attachment are strong warning signs, and the course states that the file hash was verified as malicious. The alert ticket is marked Escalated, but I have not contacted a real Level 2 analyst. I would ask the response team to confirm whether the attachment ran, identify any affected systems, and preserve the relevant email and endpoint evidence. No active infection is confirmed by the ticket.

Source: Incident handler’s journal. Course simulation; narrative records source claims, not independently reverified actions. [Journal index](README.md).
