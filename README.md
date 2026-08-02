# VForce Platform UAT

Public **User Acceptance Testing** for the VForce platform. This is the open home for UAT participants to review the platform from the **UI/UX** perspective and report defects.

## What's here
- **`/uat`** — the UAT plan: UI/UX test scenarios you work through (what to do on screen, what to expect).
- **The Defect board** (Projects tab) — where reported defects are triaged and tracked to resolution.

## How to participate
1. Read the UAT plan under `/uat` (or take the guided version in the LMS if you were enrolled).
2. Work through each scenario in the live UI and record **Pass / Fail / Blocked**.
3. Report a defect either way:
   - **In-app (recommended):** *Ask Mnemo → Report a defect* — it pre-fills the scenario context and files the ticket for you.
   - **Manually:** open an Issue here using the **Defect report** template.

## ⚠️ This repository is PUBLIC — confidentiality rules
Everything in this repo (issues, comments, screenshots) is **world-visible and indexed**. Do **NOT** include:
- Personal / student data or **PHI**, real names, emails, or records
- **Credentials**, tokens, API keys, or connection strings
- Internal architecture, private hostnames, or source code

Keep every report to the **UI/UX**: the steps you took, what you expected, and what actually happened. **Redact screenshots** before attaching. Sensitive captures should be stored in governed storage and linked (access-controlled), never pasted into a public issue. When in doubt, leave it out and describe it in words.

This repo is a **black-box** view of the product. The engineering work to fix a defect happens in private product repositories; this board tracks the *reviewer-facing* defect and links out to its fix.
