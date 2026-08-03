# Contributing to VForce Platform UAT

Thank you for reviewing the platform. This page covers the one thing that matters most
before you post: **what must never appear in this repository.**

## This repository is PUBLIC

Everything here — issues, comments, attachments, edit history — is world-visible and
indexed by search engines. **Editing or deleting a post does not un-publish it.** It may
already be cached, scraped, or mirrored. Treat every post as permanent and public.

## Never post these

| Category | Examples |
| --- | --- |
| Personal / student data, PHI | Real names, student IDs, dates of birth, addresses, emails, rosters, assessment results, IEP or health detail, anything FERPA-covered |
| Credentials | Passwords, tokens, API keys, session cookies, connection strings, `Authorization:` headers, QR codes for MFA |
| Internal infrastructure | Private hostnames, internal IP addresses, cluster or namespace names, database names, port maps, internal service URLs |
| Product internals | Source code, stack traces, config files, architecture detail, security findings |
| Commercial detail | Contract terms, pricing, unannounced client or district names |

If a defect cannot be described without one of the above, **do not open a public issue.**
Email your Edgent point of contact and reference the UAT scenario ID instead.

## Screenshots are the biggest leak risk

A screenshot of a live platform is the single most common way sensitive data escapes during
UAT. A capture taken to show a misaligned button routinely also contains:

- real student or staff names in a grid, sidebar, or notification behind the dialog
- the tenant name, environment banner, or an internal hostname in the browser address bar
- a session token in a URL query string
- other browser tabs, bookmarks, or an email client in the background

**Before attaching any image:**

1. Prefer describing what you saw in words. Words are usually enough.
2. If an image is genuinely needed, capture **only the affected UI region**, never the full screen.
3. Use test or synthetic data, never a real record.
4. **Redact** names, emails, IDs, and the address bar — draw solid boxes. Do not blur or
   pixelate; both can be reversed.
5. Strip metadata. Image EXIF can carry a device ID, username, or location.
6. If it cannot be redacted safely, store it in governed storage and link the
   access-controlled URL instead of pasting the image.

## How to report

Use the **Defect report** form (Issues → New issue). It is structured as Gherkin
(Given/When/Then) describing the **external use case** — what you did on screen and what you
expected. Keep it black-box: behavior only, no internals.

The in-app route (**Ask Mnemo → Report a defect**) is preferred; it pre-fills the scenario
context for you.

## If you post something sensitive by mistake

Do not just delete it and move on — deletion is not removal.

1. Tell your Edgent point of contact **immediately**. Speed matters more than embarrassment;
   nobody is in trouble for reporting fast.
2. If a credential was exposed, say so explicitly — it must be **rotated**, not just deleted.
3. Edgent will handle removal, cache purge, and any required notification.

## Accounts

Reading this repository is anonymous. **Filing an issue or commenting requires a free GitHub
account** — public visibility alone does not grant you the ability to post.
