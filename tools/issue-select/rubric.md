# Rubric: is this a good first issue?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever checks
you define here. It ships empty on purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where. Name the source
     (repo-facts block, issue body, comment thread, or the locations in
     references/evidence-guide.md). "The repo" is not a source; "the last
     5 default-branch commit dates" is.
   - Pass condition: a condition someone else could apply and get your
     answer. Prefer thresholds with numbers ("a maintainer commented
     within 30 days") over adjectives ("maintainer is responsive").
   - Weight: `required` (a fail here rejects the issue) or `preferred`
     (never changes the verdict; a nice-to-have that helps rank the
     issues you accept).

2. A verdict rule below the table: how the check grades combine into
   accept or reject, including how `unclear` is treated. The verdict
   space is binary. If you write no rule for `unclear`, the skill treats
   it as fail.

Cover what actually kills first contributions. The lecture named four
families: the maintainer is alive, the repo is in use, the scope fits a
newcomer, and nobody else is already on it. A rubric that ignores a family
will fail eval issues designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| maintainer-alive | Last 5 default-branch commits in the repo-facts block | At least 2 non-bot commits were made in the last 90 days | required |
| repo-in-use | Archived status, latest release, and last push in the repo-facts block | The repo is not archived and has had a release or recent activity within the last year | required |
| scope-fits | Issue body and comment thread | Pass unless the issue is explicitly a tracking or umbrella issue, is only a support question, has design discussion that is still unresolved, or a maintainer explicitly says the fix requires major core-internal changes. Also fail if the issue has several abandoned contribution attempts that suggest it is harder than it appears. A short description, multiple files, several steps, performance work, threading, or multiple suggested solutions do not by themselves make the issue fail. | required |
| unclaimed | Assignees and linked PRs in the repo-facts block, plus the comment thread | The issue has no assignee, no open PR working on it, and no recent comment showing someone is actively working on it | required |
| ai-policy | Contribution policy in the repo-facts block | The repo does not ban AI-assisted contributions | required |
| maintainer-responsive | Maintainer response sample in the repo-facts block | A maintainer replied to at least one sampled issue within 30 days | preferred |

## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict, they
rank accepted issues; unclear counts as fail." -->
Accept if all required checks pass. If a required check fails or is unclear, reject the issue. Preferred checks do not affect the verdict and only help rank accepted issues.