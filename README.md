# Analysis of the Supply Chain Cyberattack Against SolarWinds

This repository contains a comprehensive technical and strategic analysis of the 2020 supply chain cyberattack against SolarWinds. The report maps the penetration using the MITRE ATT&CK framework and evaluates mitigation strategies based on NIST standards. 

## Authors
*   **Deligiannis Nikolaos** (3230041)
*   **Paulou Antonios** (3230163)
*   **Institution:** Athens University of Economics and Business (AUEB) - Department of Informatics

## Overview
The SolarWinds Orion platform breach allowed the APT29 (also known as NOBELIUM or Cozy Bear) threat group to deploy the SUNBURST backdoor into approximately 18,000 organizations. This attack successfully weaponized a highly privileged network management tool to infiltrate top tech companies and 9 critical U.S. federal agencies.

## Key Report Highlights

### Part A: Summary of the Attack
*   Details the initial penetration and the strategic patience of the attackers, who waited months before deploying the malicious payload.
*   Explains how the SUNBURST backdoor was integrated into official Orion updates, compiled, and digitally signed with valid cryptographic certificates, bypassing traditional security systems.

### Part B: MITRE ATT&CK Technical Mapping
The report breaks down the attack into four distinct stages:
*   **Initial Access:** Bypassing corporate firewalls via supply chain compromise (T1195.002).
*   **Execution:** Utilizing the custom SUNSPOT malware to inject malicious code specifically during the `MsBuild.exe` compilation process, ensuring developers were not alerted (T1057).
*   **Defense Evasion & C2:** Camouflaging network traffic to mimic the legitimate SolarWinds Orion Improvement Program (OIP) protocol to communicate with Command and Control servers (T1048).
*   **Lateral Movement & Post-Exploitation:** Exploiting Identity and Access Management (IAM) systems using the sophisticated **Golden SAML** technique to forge valid login tokens and completely bypass multi-factor authentication (MFA) (T1606.002).

### Part C: Delayed Detection & Mitigations
*   Analyzes the broader operational pathologies and security culture failures that delayed detection for nearly nine months, including the infamous "solarwinds123" password exposure.
*   Proposes defensive architectures emphasizing a Zero Trust philosophy.
*   Recommends the adoption of the **NIST SP 800-161r1** framework for supply chain risk management and the **NIST SSDF (SP 800-218)** for securing the software development lifecycle.
*   Outlines specific mitigations for countering Identity Forgery (Golden SAML), including strict Active Directory Federation Services (AD FS) tiering and signing certificate key rotation.

## Full Report
The complete technical analysis can be viewed in the [SolarWinds-Report.pdf](./SolarWinds-Report.pdf) provided in this repository.
