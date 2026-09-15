<p align="center">
  <img src="assets/banner.svg" alt="M365 Weekly Report Automation — an n8n workflow banner" width="100%" />
</p>

<h1 align="center">M365 Weekly Report Automation</h1>

<p align="center">
  An AI-assisted, production-style <strong>n8n</strong> workflow that turns weekly Microsoft 365 tenant reporting into a fully automated pipeline — powered by the Microsoft Graph API.
</p>

<p align="center">
  <img alt="Platform" src="https://img.shields.io/badge/platform-n8n-FF6D5A?style=flat-square">
  <img alt="Integration" src="https://img.shields.io/badge/integration-Microsoft%20Graph%20API-0078D4?style=flat-square">
  <img alt="Nodes" src="https://img.shields.io/badge/workflow-25%20nodes-6f42c1?style=flat-square">
  <img alt="License" src="https://img.shields.io/badge/license-MIT-green?style=flat-square">
  <img alt="Status" src="https://img.shields.io/badge/status-production--oriented%20template-blue?style=flat-square">
</p>

---

## What is this?

This repository packages a complete **n8n automation** that connects to a Microsoft 365 tenant, collects organisation, licensing, and user-directory data via the **Microsoft Graph API**, calculates operational KPIs, and produces a polished reporting package — automatically, every week, with no manual effort.

It's a real-world example of **AI-era workflow automation**: instead of an administrator manually pulling reports from the Microsoft 365 admin center each week, a scheduled n8n workflow does the collection, analysis, formatting, archiving, and distribution end-to-end.

```text
Microsoft Graph  →  Normalise & Analyse  →  Excel + CSV  →  SharePoint Archive  →  Executive Email
```

## Highlights

- ⏰ **Scheduled, unattended execution** — runs weekly with app-only OAuth 2.0 authentication
- 📊 **Licence utilisation analysis** with Healthy / Watch / Critical classification
- 👥 **Full user-directory collection** with pagination, domain segmentation, and account-status analysis
- 📈 **Week-over-week KPI comparison** using n8n workflow static data
- 📁 **Automated Excel workbook + CSV exports**, archived straight to SharePoint
- 📧 **HTML executive-summary email**, sent via Microsoft Graph `sendMail`
- 🛡️ **Safe-by-default**: a configurable email-send gate and sanitised, public-safe example values

## Repository layout

```text
.
├── assets/
│   └── banner.svg                     # Repo banner (this file)
└── M365-Weekly-Report-n8n-GitHub/
    ├── README.md                      # Full project documentation
    ├── LICENSE
    ├── project.json
    ├── docs/
    │   ├── ARCHITECTURE.md            # Data flow & data model
    │   └── CONFIGURATION.md           # Configuration reference
    └── workflow/
        └── M365-Weekly-Report.json    # The importable n8n workflow
```

## Getting started

1. Open [`M365-Weekly-Report-n8n-GitHub/README.md`](M365-Weekly-Report-n8n-GitHub/README.md) for full setup, configuration, and testing instructions.
2. Import [`workflow/M365-Weekly-Report.json`](M365-Weekly-Report-n8n-GitHub/workflow/M365-Weekly-Report.json) into your n8n instance.
3. Configure the Microsoft Graph app-only OAuth 2.0 credential and the workflow's `Config` node.
4. Keep `skipEmailSend: true` while testing, then disable it once validated.

See [`docs/ARCHITECTURE.md`](M365-Weekly-Report-n8n-GitHub/docs/ARCHITECTURE.md) for the data flow and [`docs/CONFIGURATION.md`](M365-Weekly-Report-n8n-GitHub/docs/CONFIGURATION.md) for the full configuration reference.

## Technology stack

**n8n** &middot; **Microsoft Graph API** &middot; **OAuth 2.0 (client credentials)** &middot; **Microsoft Entra ID** &middot; **SharePoint / OneDrive for Business** &middot; **ExcelJS**

## License

This repository is provided under the [MIT License](M365-Weekly-Report-n8n-GitHub/LICENSE).
