# Incident Report Analysis – DoS Attack

## Scenario
Analyzed a DoS attack on a multimedia company where a 
threat actor flooded the network with ICMP packets through 
an unconfigured firewall, disrupting services for 2 hours.

## Framework Used
NIST Cybersecurity Framework (CSF)

## What I Did
- Identified root cause: unconfigured firewall
- Applied all 5 NIST CSF functions to the incident
- Developed security improvement recommendations

## NIST CSF Summary

| Function | Action Taken |
|----------|-------------|
| Identify | Found unconfigured firewall as root cause |
| Protect | Implemented firewall rules + IDS/IPS |
| Detect | Deployed network monitoring software |
| Respond | Blocked ICMP, isolated non-critical services |
| Recover | Restored critical services, updated firewall rules |

## Key Findings
- Attack Type: DoS via ICMP flood
- Root Cause: Unconfigured firewall
- Duration: 2 hours
- Resolution: Firewall rate limiting + IDS/IPS implementation

## Skills Demonstrated
NIST CSF · Incident Response · Network Security · 
DoS Attack Analysis · Firewall Configuration
