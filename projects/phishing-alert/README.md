# Phishing Alert — Escalation Rationale

**Context:** Google Cybersecurity Certificate coursework / simulation.  
**Status:** Written ticket comments present; native status extraction ambiguous.

## Evidence reviewed

The course ticket A-2703 describes a medium-severity phishing alert involving a supposed job application and bfsvc.exe. The written comments identify mismatched sender details, poor wording, and an executable presented as a resume. The course states that the file hash was already confirmed malicious.

## Decision recorded

The response recommends escalation to a level-two analyst under the supplied playbook. It explicitly leaves file execution, infection, and affected devices unconfirmed. No real analyst was contacted through this portfolio.

## Validation limit

The readable status field appears as “EscalatedOpen”, so the actual native status selection is not independently validated. The comments clearly record escalation intent. Raw email addresses, public IPs, and the attachment password are omitted from this public version because they are unnecessary to demonstrate the analysis.

See also [journal entry 3](../incident-journal/entry-03.md).

## Evidence and attribution

Adapted from the Drive document “Alert ticket”. Source response text and supplied scenario material may coexist in course templates. This portfolio was organized and edited with AI assistance; it does not claim independent authorship of course materials or production security work. See [source register](../../docs/source-register.md).

[Back to portfolio](../../README.md)
