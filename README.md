# CCSA110-Threat-Prevention-Fundamentals
# Assignment: Configure and Validate a Check Point Threat Prevention Policy
This repository contains my CCSA110 practical lab report and supporting evidence for configuring and reviewing a Check Point Threat Prevention policy in a Check Point R82 lab environment.
- Student Information
- Field	Details
- Programme	CCSA Cohort 11
- Institution	International Cybersecurity & Digital Forensics Academy (ICDFA)
- Student Reference	C11/26/CCSA/17114
- Lab Platform	Check Point R82
- Management Server	icdfar82smsv2
- Policy Package	Orion-Layers
- Cluster Object	icdfa-r82-cluster


Repository Structure
CCSA110-Threat-Prevention-Fundamentals/
├── README.md
├── .gitignore
├── docs/
│   ├── CCSA110_FinalLab_C11-26-CCSA-17114.pdf
│   └── CCSA110_FinalLab_C11-26-CCSA-17114.docx
└── evidence/
    └── figures/
        ├── 01.png
        ├── 02.png
        ├── 03.png
        ├── 04.png
        ├── 05.png
        ├── 06.png
        └── 07.png
The docs/ directory is intended for the final report in PDF and editable Word formats. The evidence/figures/ directory contains supporting screenshots extracted for the report.
Lab Overview
The practical focused on reviewing the gateway configuration, identifying enabled Threat Prevention capabilities, creating or reviewing a custom Threat Prevention profile, configuring a pilot policy rule, installing the policy, and examining IPS events.

The Threat Prevention blades visible in the gateway properties included:
- Intrusion Prevention System (IPS)
- Anti-Bot
- Anti-Virus
- Threat Emulation
- Threat Extraction
- Zero Phishing
The custom profile displayed in SmartConsole was:

CCSA110-TP-C11_26_CCSA_17114

The policy package used was Orion-Layers, and the pilot rule was labelled Pilot Rule.
Policy Installation Evidence
The SmartConsole policy installation workflow displayed successful status indicators for the listed installation targets. The detailed installation evidence is included in the report.

A successful policy installation indicates that the policy installation operation completed for the displayed targets. It does not, by itself, prove that every Threat Prevention control was exercised successfully against a test workload.
IPS Event Analysis
Two IPS events were reviewed during the practical:
Detect event
- Protection: Web Server Exposed Git Repository Information Disclosure
- Action: Detect
- Service: HTTPS / TCP 443
- The event was associated with the pilot rule and the custom Threat Prevention profile.
Prevent event
- Protection: Zyxel P660HN-T1A Command Injection
- CVE: CVE-2017-18368
- Action: Prevent
- Service: HTTP / TCP 80
- The event was associated with the Autonomous Threat Prevention / Perimeter (Recommended) profile.
Important: These records are separate events involving different protections, source and destination addresses, services, cluster members, and policy/profile contexts. They are not a controlled, like-for-like comparison of Detect and Prevent actions.
Connectivity Checks and Validation Limitations
The test client used during the connectivity checks was:
- Hostname: labvm
- Interface: ens32
- IPv4 address: 10.1.1.210/24
- Default gateway: 10.1.1.250
The client could reach its default gateway. However, attempts to ping the cluster virtual IP addresses 172.17.1.10 and 172.17.2.11 were unsuccessful. The network path and routing between the test client and the cluster were not fully established during the lab.

The approved internal application/service endpoint required for baseline and post-change application testing was not available. Therefore:
- Baseline application connectivity testing was not completed.
- Post-change application connectivity testing was not completed.
- Successful end-to-end application validation is not claimed.
- The ping checks are recorded as diagnostic observations only; they do not replace application-level validation.
These limitations are documented to distinguish configuration and installation evidence from functional validation.
Key Learning Outcomes
Through this practical, I reviewed how to:
1. Identify a Check Point gateway and its enabled Threat Prevention capabilities.
2. Work with Threat Prevention profiles and a pilot policy rule in SmartConsole.
3. Review policy installation results.
4. Interpret IPS log fields, including protection name, action, source, destination, and service.
5. Distinguish between Detect and Prevent events without treating unrelated events as a controlled test.
6. Document validation gaps and avoid claiming results that were not established by the available evidence.
Report
The full practical procedure, observations, analysis, screenshots, limitations, and conclusion are documented in the final report:
- docs/CCSA110_FinalLab_C11-26-CCSA-17114.pdf
- docs/CCSA110_FinalLab_C11-26-CCSA-17114.docx
References
- Check Point Software Technologies. Threat Prevention Administration Guide.
- Check Point Software Technologies. R82 Security Management Administration Guide.
- ICDFA CCSA110 course materials: Threat Prevention Fundamentals.
Refer to the final report for the references and supporting discussion used in the assignment.
Disclaimer
This repository documents an academic lab exercise in an authorized training environment. IP addresses, hostnames, object names, and event details are included as lab evidence. No production credentials, passwords, private keys, or other authentication secrets should be committed to this repository.
