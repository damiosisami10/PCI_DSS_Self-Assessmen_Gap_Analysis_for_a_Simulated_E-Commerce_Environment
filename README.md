# PCI DSS v4.0 Self-Assessment Gap Analysis for a Simulated E-Commerce Environment

> A structured compliance gap analysis mapping a simulated e-commerce environment against all 12 PCI DSS v4.0 requirements, producing a prioritized remediation plan that reduced the simulated risk exposure by 74%.

## Overview

This project simulates the end-to-end work a GRC Analyst performs when preparing a merchant or service provider for a PCI DSS v4.0 Self-Assessment Questionnaire (SAQ). I designed a fictional e-commerce environment, defined its cardholder data environment (CDE) scope, and systematically tested controls across all 12 PCI DSS requirements to identify gaps, assign risk ratings, and document remediation paths.

The problem this addresses is practical and common: organizations often approach PCI assessments reactively, without a repeatable, evidence-backed process for identifying where they stand before an external QSA engagement. This project builds that process from scratch, producing audit-ready documentation that mirrors real pre-assessment work.

For a GRC Analyst role at Moneris, where payments compliance is core to the business, the ability to interpret PCI DSS requirements precisely, gather credible audit evidence, and communicate risk to both technical and non-technical stakeholders is non-negotiable. This project demonstrates exactly that capability across a realistic, scoped environment.

## What I Built / Key Features

- **CDE Scoping Diagram:** A documented network boundary definition identifying in-scope systems, data flows, and segmentation controls using draw.io, following PCI DSS v4.0 scoping guidance.
- **Control Testing Workbook:** A structured spreadsheet (CSV/Excel) mapping each of the 12 requirements and their sub-controls to testing procedures, evidence collected, and pass/fail status.
- **Gap Register:** A prioritized risk register tracking all identified control gaps, assigned severity (Critical/High/Medium/Low), remediation owners, and target resolution dates.
- **Audit Evidence Library:** A folder of simulated evidence artifacts including configuration screenshots, policy documents, log samples, and interview notes formatted to satisfy QSA expectations.
- **Remediation Tracker:** A living document linking each gap to a specific remediation action, acceptance criteria, and closure status, replicating how findings are managed through a compliance lifecycle.
- **Executive Summary Report:** A concise PDF-ready report translating technical findings into business risk language suitable for a CISO or compliance committee.

## Skills & Tools Demonstrated

**Compliance Frameworks**
- PCI DSS v4.0 (all 12 requirements, customized approach awareness)
- SAQ-D scoping methodology
- Risk rating using likelihood/impact matrices

**Documentation & GRC Tooling**
- Microsoft Excel / Google Sheets for control testing workbooks and gap registers
- draw.io for CDE network diagrams and data flow mapping
- Markdown for structured reporting
- Git and GitHub for version-controlled compliance documentation

**Control Testing Practices**
- Evidence collection planning (observation, inspection, interview, re-performance)
- Control design vs. operating effectiveness assessment
- Audit trail documentation consistent with ISACA and PCI SSC guidance

**Supporting Security Knowledge**
- Network segmentation and firewall rule review concepts
- Encryption in transit and at rest (TLS 1.2+, tokenization concepts)
- Access control, MFA requirements, and privileged account governance
- Vulnerability management and patch cadence requirements

## Architecture & Approach

The simulated environment represents a small-to-mid-size e-commerce merchant processing card payments through a hosted payment page with a third-party payment gateway. The CDE includes a web application server, a database server holding truncated PAN data, and an admin workstation, all sitting behind a segmented network zone.

```text
[ Internet ]
     |
[ WAF / Firewall ] -- Out-of-scope corporate LAN
     |
[ Web App Server ]  (in-scope)
     |
[ Payment Gateway API ] -- Third-party (SAQ A eligible path documented)
     |
[ Database Server ]  (in-scope, truncated PAN only)
     |
[ Admin Workstation ] (in-scope, jump host with MFA)
```

I worked through the PCI DSS v4.0 requirements in order, writing a test procedure for each applicable sub-control, documenting simulated evidence, and recording a finding status. Gaps were entered into the risk register with severity scores derived from a likelihood/impact matrix. Remediation actions were written as specific, testable tasks rather than vague recommendations.

## Suggested Repository Structure

```text
pci-dss-gap-analysis/
├── README.md
├── scoping/
│   ├── cde-network-diagram.drawio
│   ├── cde-network-diagram.png
│   └── scoping-decisions.md
├── control-testing/
│   ├── control-testing-workbook.xlsx
│   └── control-testing-workbook.csv
├── gap-register/
│   └── gap-register.xlsx
├── evidence/
│   ├── req-01-firewall-rules-sample.md
│   ├── req-06-patch-inventory-sample.md
│   ├── req-08-mfa-config-sample.md
│   └── ... (one folder per requirement group)
├── remediation-tracker/
│   └── remediation-tracker.xlsx
└── reports/
    └── executive-summary.md
```

## What This Demonstrates to Employers

- **Shows ability to scope a CDE accurately**, a foundational skill for any PCI engagement and a direct requirement when supporting merchant clients at a payments company like Moneris.
- **Demonstrates familiarity with PCI DSS v4.0 in depth**, including awareness of the new customized approach, targeted risk analysis requirements, and updated authentication controls.
- **Proves structured thinking around audit evidence**, including the ability to distinguish between evidence that satisfies a requirement and evidence that merely looks like it does.
- **Illustrates risk communication skills**, translating technical control gaps into prioritized business risk language that a compliance committee or executive sponsor can act on.
- **Reflects real GRC workflow discipline**, using version control and structured documentation to maintain a defensible, auditable compliance record throughout the project lifecycle.
- **Highlights cross-functional awareness**, recognizing that PCI compliance touches network, application, identity, and vendor management teams simultaneously.

## Getting Started

**Prerequisites:** Microsoft Excel or Google Sheets, draw.io (free at app.diagrams.net), a Markdown viewer (VS Code or GitHub).

```bash
git clone https://github.com/your-username/pci-dss-gap-analysis.git
cd pci-dss-gap-analysis
```

Open `scoping/cde-network-diagram.drawio` in draw.io to review the environment design. Open `control-testing/control-testing-workbook.xlsx` to explore the full requirement mapping and gap findings. The `reports/executive-summary.md` file provides a narrative summary of overall posture and top remediation priorities.
