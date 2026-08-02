# UAT Plan

The UI/UX UAT scenarios live here, written as **Gherkin (Given/When/Then) for the external use case** — what a user does on screen and expects to see. Two tracks:

- **`platform-uat`** — full platform (Access & SSO · Flow · Lakehouse + ODBC/BI · Askura · LMS · Governance · Cross-cutting UX · Sign-off)
- **`rcsd-uat`** — the RCSD subset (Access · Lakehouse + ODBC/BI · Askura · LMS · Governance · Sign-off)

A guided, tracked version (with per-scenario Pass/Fail capture) is delivered through the LMS for enrolled reviewers; this repo is the open, black-box copy plus the defect board.

> Scenarios are being staged here now. Everything is **UI/UX black-box** — no internal architecture, hostnames, or data.
