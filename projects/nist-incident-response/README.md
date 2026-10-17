# NIST Framework — ICMP Flood Response

**Context:** Google Cybersecurity Certificate coursework / simulation.  
**Status:** Written scenario analysis complete; no live incident investigated.

## Summary

The company’s internal network stopped working for two hours because an attacker flooded it with ICMP packets. The firewall was not properly configured, so it allowed the flood of traffic through and prevented employees from accessing network resources. The response team blocked incoming ICMP traffic, temporarily shut down non-essential services, and restored essential services. The security team then added firewall limits, checks for fake source IP addresses, and monitoring tools to help prevent and detect similar attacks.

## Identify

The company experienced a denial-of-service (DoS) attack. An attacker flooded the internal network with ICMP packets through a firewall that was not properly configured. This overwhelmed the network and stopped employees from accessing network resources for two hours.

## Protect

The company should keep its firewall properly configured and limit incoming ICMP traffic so it cannot overwhelm the network. It should also check for fake source IP addresses and use an intrusion prevention system to filter suspicious traffic. Regular firewall reviews and staff training can help keep these protections working.

## Detect

The company should monitor network traffic for sudden increases in ICMP packets and other unusual activity. Network monitoring tools and an intrusion detection system should alert the security team when they spot suspicious traffic. The team should review firewall logs to understand where the traffic is coming from and investigate possible attacks.

## Respond

The security team should investigate the alert and block or limit the harmful traffic. If needed, it should temporarily stop non-essential services to protect critical services. The team should save relevant logs, document its actions, and keep IT staff and management informed. After the incident, it should review what happened and improve the response plan.

## Recover

Once the harmful traffic is under control, the team should restore critical network services first, then bring back non-essential services. It should test that employees can access the resources they need and monitor the network for signs of another attack. The team should keep staff informed about service availability and update the recovery plan with lessons from the incident.

## Framework context

This follows the five-function version taught in this activity. It is a course-era mapping, not a claim to cover every function in newer framework versions. The scenario describes DoS; multiple attack sources were not established. Implemented measures refer to events stated in the fictional scenario; future measures are recommendations.

## Evidence and attribution

Adapted from the Drive document “Incident report analysis”. Source response text and supplied scenario material may coexist in course templates. This portfolio was organized and edited with AI assistance; it does not claim independent authorship of course materials or production security work. See [source register](../../docs/source-register.md).

[Back to portfolio](../../README.md)
