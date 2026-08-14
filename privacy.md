---
title: Privacy Policy — Bugbridge for Jira
---

# Privacy Policy

**DataForte AB** · Tant Gröns väg 54, 147 60 Uttran, Sweden
Contact: hello@dataforteab.com
Last updated: 14 August 2026

This policy describes how the Atlassian Marketplace app **Bugbridge for Jira** ("the app")
handles data. The app is built on Atlassian Forge and runs on Atlassian's infrastructure.

## What the app does with your data

Bugbridge connects a BugSnag project to a Jira Cloud site. To do that it processes:

- **BugSnag error metadata** received from the BugSnag Data Forwarding webhook you configure: the
  error id, project id, exception class, message, severity, context (culprit) and release stage,
  plus the link back to BugSnag.
- **Jira issue data** needed to create and update issues: project key, issue type, issue key and
  the comments the app itself writes.
- **Configuration you enter**: your project mapping rules and the BugSnag credentials described
  below.

The app does not collect analytics, does not profile users, and does not sell or share data with
anyone. DataForte AB has no access to your Jira site or your BugSnag account.

## Where data is stored

All app data lives in **Forge Key-Value Store**, inside Atlassian's cloud infrastructure, scoped to
your installation. DataForte AB operates no servers and stores no copy of your data.

Stored per installation:

| Data | Purpose |
|---|---|
| BugSnag personal auth token and optional webhook shared secret | authenticating to the BugSnag API, verifying incoming webhooks — stored **encrypted** in Forge secret storage |
| Project mapping rules | deciding which BugSnag projects create issues in which Jira projects |
| Link index (BugSnag error id ↔ Jira issue key, project id, timestamps) | deduplicating recurring errors and syncing status both ways |
| BugSnag snapshot per linked Jira issue (exception class, message, severity, release stage, URL) | rendering the BugSnag panel without calling BugSnag on every view |

## Data sent outside Atlassian

The app calls the BugSnag API at a single host, `https://api.bugsnag.com`. What is sent: the BugSnag
error id and project id, your BugSnag personal auth token for authentication, and — when you move a
Jira issue to a done status or reopen it — the instruction to mark that error **"fixed"** or
**"open"**. No Jira content is sent to BugSnag.

No other external service receives any data.

## Personal data

The app does not intentionally process personal data. Two indirect cases are worth naming:

- A BugSnag error payload may contain personal data if your own application puts it there — for
  example in the message or context. The app copies the exception class, message and severity into a
  Jira issue in your own site.
- If a rule sets a default assignee, that Jira user's Atlassian account id is stored in the rule.

DataForte AB acts as a **data processor** for whatever passes through the app; you remain the
**controller**. There are no sub-processors: nothing leaves Atlassian's infrastructure except the
BugSnag calls described above, and BugSnag is your own provider under your own agreement with them.

## Legal basis for processing

Where the GDPR or UK GDPR applies, we process data on two bases: to **perform the contract** under
which the app is provided to you (Art. 6(1)(b)), and the **legitimate interest** (Art. 6(1)(f)) you
and we share in operating the integration you configured — creating, deduplicating and synchronising
issues — which cannot be achieved less intrusively, because the app handles only the data those
functions require. As processor we act on your documented instructions as controller; you determine
the legal basis for the underlying error and issue data.

## International transfers

Data is stored and processed within your Atlassian Cloud tenant, in the region Atlassian assigns to
it. The only cross-border flow is to your own BugSnag account, reached through BugSnag's single API
host. Any transfer of personal data outside the EEA is covered by the standard contractual clauses
and safeguards that Atlassian and BugSnag maintain under their own agreements with you; DataForte AB
introduces no additional transfer of its own.

## Retention and deletion

Data lives for as long as the app is installed. **Uninstalling the app deletes its Forge storage**,
including the encrypted credentials. Jira issues the app created remain in your Jira site, because
they are your issues.

To request information or deletion at any other time, write to hello@dataforteab.com. We answer
within 30 days.

## Your rights

Under the GDPR you may request access to, correction of, or deletion of personal data, and you may
lodge a complaint with the Swedish data protection authority (Integritetsskyddsmyndigheten).

## Security and incident notification

The BugSnag personal auth token and webhook shared secret are held in Forge **encrypted secret
storage** and are never returned to the admin UI or written to logs. Incoming webhooks are verified
with an HMAC-SHA256 signature when a shared secret is configured. Because the app stores data only
inside your Atlassian tenant, a breach of that stored data would be an Atlassian platform event
handled under Atlassian's incident process; where we become aware of an incident affecting data the
app processes, we will notify you at the vendor contact on your installation without undue delay.

## Children

The app is a business tool for software teams. It is not directed to children, and we do not
knowingly process children's data.

## Changes

Material changes to this policy will be published on this page with a new "last updated" date.
