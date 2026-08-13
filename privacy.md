---
title: Privacy Policy — Bugbridge for Jira
---

# Privacy Policy

**DataForte AB** · Tant Gröns väg 54, 147 60 Uttran, Sweden
Contact: dataforteab@gmail.com
Last updated: 12 August 2026

This policy describes how the Atlassian Marketplace app **Bugbridge for Jira** ("the app")
handles data. The app is built on Atlassian Forge and runs on Atlassian's infrastructure.

## What the app does with your data

Bugbridge connects a BugSnag organisation to a Jira Cloud site. To do that it processes:

- **BugSnag issue metadata** received from the webhook you configure in BugSnag: issue id, title,
  culprit, level, environment, event count, short id and the link back to BugSnag.
- **Jira issue data** needed to create and update issues: project key, issue type, issue key and
  the comments the app itself writes.
- **Configuration you enter**: your BugSnag organisation slug, the project mapping rules, and the
  BugSnag credentials described below.

The app does not collect analytics, does not profile users, and does not sell or share data with
anyone. DataForte AB has no access to your Jira site or your BugSnag organisation.

## Where data is stored

All app data lives in **Forge Key-Value Store**, inside Atlassian's cloud infrastructure, scoped to
your installation. DataForte AB operates no servers and stores no copy of your data.

Stored per installation:

| Data | Purpose |
|---|---|
| BugSnag organisation slug and API base | knowing which BugSnag org and region to talk to |
| BugSnag API token and webhook client secret | authenticating to BugSnag, verifying webhooks — stored **encrypted** in Forge secret storage |
| Project mapping rules | deciding which BugSnag projects create issues in which Jira projects |
| Link index (BugSnag issue id ↔ Jira issue key, event count, timestamps) | deduplicating recurring errors and syncing status both ways |
| BugSnag snapshot per linked Jira issue (title, level, event count, URL, short id) | rendering the BugSnag panel without calling BugSnag on every view |

## Data sent outside Atlassian

The app calls the BugSnag API at `api.bugsnag.com`, depending on your
organisation's region. What is sent: your BugSnag organisation slug, the BugSnag issue id, your BugSnag
API token for authentication, and — when you close a Jira issue — the instruction to resolve that
issue. No Jira content is sent to BugSnag.

No other external service receives any data.

## Personal data

The app does not intentionally process personal data. Two indirect cases are worth naming:

- A BugSnag error payload may contain personal data if your own application puts it there. The app
  copies the issue title, culprit and level into a Jira issue in your own site.
- If a rule assigns issues to a Jira user, that user's Atlassian account id is stored in the rule.

DataForte AB acts as a data processor for whatever passes through the app; you remain the
controller. There are no sub-processors: nothing leaves Atlassian's infrastructure except the BugSnag
calls described above, and BugSnag is your own provider under your own agreement with them.

## Retention and deletion

Data lives for as long as the app is installed. **Uninstalling the app deletes its Forge storage**,
including the encrypted credentials. Jira issues the app created remain in your Jira site, because
they are your issues.

To request information or deletion at any other time, write to dataforteab@gmail.com. We answer
within 30 days.

## Your rights

Under the GDPR you may request access to, correction of, or deletion of personal data, and you may
lodge a complaint with the Swedish data protection authority (Integritetsskyddsmyndigheten).

## Changes

Material changes to this policy will be published on this page with a new "last updated" date.
