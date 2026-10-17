# Parking Lot USB — Threat Analysis

**Context:** Google Cybersecurity Certificate coursework / simulation.  
**Status:** Three written answers complete; no device examined.

## Information exposure

The USB contains a mix of personal and work-related information, including family and pet photos, a new hire letter, employee schedules, budget information, and a resume. Some files may contain personally identifiable information and internal hospital information that should not be stored on an unsecured removable device.

## Attacker mindset

An attacker could use the personal information on the USB for social engineering, phishing, or identity-related attacks against Jorge or other employees. Work files such as schedules, hiring documents, and budget information could also reveal internal operations and help an attacker target the hospital more effectively.

## Proposed controls

The hospital should train employees never to connect unknown USB drives to company systems and require suspicious devices to be given to the security team. Technical controls could restrict USB ports and automatically scan approved removable media for malware. Unknown devices should only be examined in an isolated virtual environment. Policies should also prohibit storing sensitive work data on personal USB drives and require encrypted, organization-approved devices when removable storage is necessary.

## Review note

The USB contents and hospital are fictional scenario details. An isolated virtual machine alone is not proof of safe handling of unknown physical hardware. The source’s proposed examination method remains untested; practical examination needs an authorized lab and reviewed handling procedure. No malware, exfiltration, or successful attack is established.

## Evidence and attribution

Adapted from the Drive document “Parking lot USB exercise”. Source response text and supplied scenario material may coexist in course templates. This portfolio was organized and edited with AI assistance; it does not claim independent authorship of course materials or production security work. See [source register](../../docs/source-register.md).

[Back to portfolio](../../README.md)
