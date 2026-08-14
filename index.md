---
title: Bugbridge for Jira
---

# Bugbridge for Jira

BugSnag errors become tracked Jira work — created automatically, deduplicated when they recur, and
kept in sync in both directions.

An Atlassian Forge app by **DataForte AB**, available on the Atlassian Marketplace.

## What it does

- A BugSnag error creates a Jira issue with its exception class, message, severity, release stage and
  a link back to BugSnag.
- The same error recurring updates the existing linked issue instead of filling your backlog with
  duplicates.
- Moving the Jira issue to a done status marks the error **fixed** in BugSnag; marking it fixed in
  BugSnag leaves a note on the Jira issue, and reopening the issue marks the error **open** again.
- A conditional **BugSnag** panel on each linked issue shows the current error snapshot.
- Rules per BugSnag project decide the target Jira project, issue type, default assignee, and which
  severities and release stages create work.
- An hourly reconciliation scan picks up anything a dropped webhook would have lost.

## Pages

- [Support](support.html)
- [Privacy Policy](privacy.html)
- [Terms of Service](terms.html)

---

DataForte AB · Tant Gröns väg 54, 147 60 Uttran, Sweden · hello@dataforteab.com
