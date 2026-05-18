# Beatrice-grc-risk-register
# Technical Architecture: Inline AI Compliance Auditing

This document details the data structure and prompt engineering used to turn a standard spreadsheet into an automated compliance verification engine using Gemini.

## Data Schema Matrix

| Field Name | Data Type | Description / Source |
| :--- | :--- | :--- |
| **Control Requirement** | Text (String) | Rigid specifications pulled directly from NIST SP 800-53 Rev. 5 baseline documentation. |
| **Organizational Evidence** | Text (String) | Real-world engineering telemetry, audit logs, and status updates from internal platforms like ServiceNow. |
| **AI Auditor Assessment** | Formula Output | Dynamic cell analysis generated via generative AI logic. |

## The Core Generative Prompt

The following prompt is injected into the compliance matrix cells to evaluate organizational evidence against regulatory requirements:

```excel
=AI("You are a Senior GRC Auditor. Compare the organizational evidence provided against the NIST 800-53 requirement. 

Perform the following tasks:
1. Assign a clear status: [Compliant], [Partially Compliant], or [Non-Compliant].
2. Identify any specific gaps causing project roadblocks or delays.
3. Provide one practical, direct remediation action that the project management team can implement immediately to keep milestones on track.", A2:B2)
