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
Tell your product lead — your Edgent point of contact — privately, and reference the UAT
scenario ID here instead.

## When the defect *is* the security control

Some scenarios test the controls that keep one organization's data away from everyone else:
sign-on and tenant scoping, the audit ledger, relationship-scoped permissions, masking and
suppression, and the same checks repeated from a SQL client. On those, a **Fail** is not a
cosmetic bug — it is a live weakness in a protection that is currently switched on for real
people's data. Written up in public, the report itself becomes the second problem.

So when one of those fails:

- **Report the observable behavior, and stop there.** *"I could see the other tenant's table
  list"* is a complete finding. Which table, whose data, and what was in it are not.
- **Never write down a way around the control.** If you found one, that is the most valuable
  thing you will produce — and exactly the thing that must not be published. Give it to your
  product lead privately and reference only the scenario ID here.
- **Never write down data the control was supposed to hide.** On a masking or suppression
  failure, that the values were visible *is* the finding; reproducing them turns one
  disclosure into two.
- **Do not post reproduction steps** for an access-control defect. They are a recipe. Say
  which scenario it was and hand the steps over privately.

Each scenario issue repeats the part of this that applies to it, at the point where you
would otherwise be tempted to paste something.

## Screenshots are the biggest leak risk

A screenshot of a live platform is the single most common way sensitive data escapes during
UAT. A capture taken to show a misaligned button routinely also contains:

- real student or staff names in a grid, sidebar, or notification behind the dialog
- the tenant name, environment banner, or an internal hostname in the browser address bar
- a session token in a URL query string
- other browser tabs, bookmarks, or an email client in the background

**A screenshot is never mandatory.** No scenario in this UAT requires one, and on the
scenarios described in *When the defect is the security control* above, the screen under test
*is* the one displaying protected data — there, the right answer is to describe what you saw
in words and attach nothing at all.

**Before attaching any image:**

1. Prefer describing what you saw in words. Words are usually enough.
2. If an image is genuinely needed, capture **only the affected UI region**, never the full screen.
3. Use test or synthetic data, never a real record.
4. **Redact** names, emails, IDs, and the address bar — cover them with **solid opaque
   boxes**, or crop the region out of the picture entirely. **Do not blur or pixelate; both
   can be reversed**, and an image that merely *looks* redacted is more dangerous than one
   that obviously is not.
5. Strip metadata. Image EXIF can carry a device ID, username, or location.
6. If it cannot be redacted safely, store it in governed storage and link the
   access-controlled URL instead of pasting the image.

## How to report

Use the **Defect report** form (Issues → New issue). It is structured as Gherkin
(Given/When/Then) describing the **external use case** — what you did on screen and what you
expected. Keep it black-box: behavior only, no internals.

Include enough steps that somebody else could reproduce it — **except** where the defect is a
governance or access-control failure, for which reproduction steps are withheld and given to
your product lead privately (see above).

The in-app route (**Ask Mnemo → Report a defect**) is preferred; it pre-fills the scenario
context for you. If a capture might contain sensitive or personal data, Mnemo prompts you to
redact it or route it to governed storage before attaching — follow that prompt rather than
attaching the raw image yourself.

## If you post something sensitive by mistake

Do not just delete it and move on — deletion is not removal.

1. Tell your product lead — your Edgent point of contact — **immediately**. Speed matters
   more than embarrassment; nobody is in trouble for reporting fast.
2. If a credential was exposed, say so explicitly — it must be **rotated**, not just deleted.
3. Edgent will handle removal, cache purge, and any required notification.

## Accounts

Reading this repository is anonymous. **Filing an issue or commenting requires a free GitHub
account** — public visibility alone does not grant you the ability to post.
