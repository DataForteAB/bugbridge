---
title: Support — Bugbridge for Jira
---

# Support

**Bugbridge for Jira** is built and supported by **DataForte AB**.

- **Email:** hello@dataforteab.com
- **Language:** English
- **Hours:** Swedish business days, 09:00–17:00 CET
- **First response:** within two business days

## Before you write

Most problems fall into one of these:

**No Jira issues are being created.** Check three things in order: the webhook URL from the app's
admin page is set as a **Data Forwarding** webhook on that BugSnag project; a rule exists for that
project; and the error passes the rule's severity and release-stage filters.

**Marking a Jira issue done does not mark the error fixed in BugSnag.** The BugSnag personal auth
token needs **write** access — a read-only token can read errors but cannot change their status.
Re-save the token on the admin page; it verifies the token against `https://api.bugsnag.com`.

**The BugSnag panel is missing on an issue.** The panel only appears on issues Bugbridge linked. On
issues created before the panel shipped, or on issues the app did not create, the marker property is
absent.

**The subscription lapsed.** Issue creation and status sync stop; rules, links and the panel stay.
Renewing resumes everything with no reconfiguration.

When you write, include your Jira site URL, your BugSnag project id, the BugSnag error link and
roughly when it happened — that is usually enough to find it in the logs.

## Links

- [Privacy Policy](privacy.html)
- [Terms of Service](terms.html)
