# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**Issue link**

[The individual Path Review issue page. A link to the repository or the issue list
does not satisfy this field.]
https://github.com/codepath/pathreview-ai301-fa26-s3/issues/72


**Verdict output**

[Your skill's live-mode output for this issue, pasted verbatim and ending with the
fenced JSON verdict block. A summary does not satisfy this field.]
Re-checking #72 for any change since the last grading run, then grading it on its own.

Live mode. #72 is in the scoped repo (codepath/pathreview-ai301-fa26-s3), so it is a valid candidate. Nothing has changed on it since the earlier run today — still open, unassigned, one comment, zero PRs in the repo.

Check-by-check

- maintainer-alive — pass. Last 5 default-branch commits are all non-bot, by Aburke225: three on 2026-09-16, two on 2026-08-24. Rubric wants ≥2 non-bot within 90 days of today (2026-09-23).
- repo-in-use — pass. archived: false, last push 2026-09-16 (7 days ago). No releases exist, but the condition reads "a release or recent activity within the last year."
- scope-fits — pass. One bounded bug across two named files, with the expected behavior spelled out: "Verification against a malformed hash should fail closed (return False), not raise." No umbrella/tracking framing, no support question, no unresolved design debate, no maintainer saying it touches core internals, and no abandoned attempts. Estimated 1–2 hours.
- unclaimed — pass. assignees: []; the repo has 0 pull requests in any state, so no PR is working on it. The one comment (sseid4, 2026-09-22) is a classmate claim, which the Path Review house rule explicitly waives — "other students' claim comments do not block an issue." Claim it anyway; credit attaches to the PR you open.
- ai-policy — pass. No CONTRIBUTING.md at root or in .github/, no AI_POLICY.md. docs/CONTRIBUTING.md (6.6 KB) has no AI-contribution language, and the PR template asks only for green CI and removal of the xfail marker. Silence passes.
- maintainer-responsive (preferred — does not affect the verdict) — pass. Aburke225 (COLLABORATOR) replied on #52 and #43 on 2026-09-16, 6 days after each opened.

All required checks pass → accept. Worth noting as a reason to prefer it: the fix is already covered by tests/unit/test_security.py carrying an @pytest.mark.xfail for manifest id H-05, so you get a pass/fail signal on your change without writing the test harness yourself.

```json
{
  "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/72",
  "checks": [
    {"name": "maintainer-alive", "grade": "pass", "evidence": "Last 5 default-branch commits all non-bot by Aburke225: 2026-09-16 (x3), 2026-08-24 (x2) — all within 90 days of 2026-09-23"},
    {"name": "repo-in-use", "grade": "pass", "evidence": "archived: false; last push 2026-09-16, 7 days before today"},
    {"name": "scope-fits", "grade": "pass", "evidence": "Bounded bug in 2 named files with stated expected behavior: 'Verification against a malformed hash should fail closed (return False), not raise'; no umbrella, support question, unresolved design, or abandoned attempts"},
    {"name": "unclaimed", "grade": "pass", "evidence": "assignees: []; repo has 0 PRs in any state; sole claim comment (sseid4, 2026-09-22) is a classmate claim waived by the Path Review house rule"},
    {"name": "ai-policy", "grade": "pass", "evidence": "No CONTRIBUTING.md at root or .github/, no AI_POLICY.md; docs/CONTRIBUTING.md contains no AI-contribution language"},
    {"name": "maintainer-responsive", "grade": "pass", "evidence": "Aburke225 (COLLABORATOR) replied on #52 and #43 on 2026-09-16, 6 days after each opened"}
  ],
  "verdict": "accept"
}
```

**The verdict must record `accept` for this issue.** Choose an issue your own skill
accepts. If your skill rejects every candidate you try, that is a signal about your
rubric rather than about the issues: revise it and re-run — retries are unlimited and a
partial re-run costs about $0.20 — or run the skill on different candidates. Output
recording `reject` for the issue you chose earns no credit for this field.

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

[The agreement score of each run you did, in order. A single run is a complete answer if
only one run occurred. **The last score in your list must match the agreement line in the
`eval-run.txt` you committed** — that file is the record of your final run.]
`agreement: 16/20 scored items  (bar: 18/20: below the bar)`

`agreement: 2/4 scored items`

`agreement: 1/2 scored items`

`agreement: 1/1 scored items`

`agreement: 19/20 scored items  (bar: 18/20: PASS)`


**Issue analysis**

[One scored issue, identified by id (`issue-01` through `issue-20`; the `calib-`
issues are not scored). State your rubric's decision, the gold label, and the
reasoning that produced your rubric's result.]
`issue-19`

`issue-19  accept  accept  yes`

My rubric's final decision was `accept`, and the gold label was `accept`. Earlier versions of my rubric rejected this issue because `scope-fits` treated the multiple possible causes and solutions as evidence that the task was too open-ended. The issue itself still describes one specific problem: selecting large subgraphs in proof mode freezes the UI. The possible implementation approaches did not make the underlying task an unresolved design problem, so after revising the scope check the rubric accepted it.


**Check rationale**

[One check from the `rubric.md` uploaded to `tools/issue-select/`, quoted as it is
currently written, with the reasoning behind its current form.]
`| scope-fits | Issue body and comment thread | Pass unless the issue is explicitly a tracking or umbrella issue, is only a support question, has design discussion that is still unresolved, or a maintainer explicitly says the fix requires major core-internal changes. Also fail if the issue has several abandoned contribution attempts that suggest it is harder than it appears. A short description, multiple files, several steps, performance work, threading, or multiple suggested solutions do not by themselves make the issue fail. | required |`

I revised this check because my earlier version was too strict about issues that contained several steps or possible technical approaches. That caused `issue-19` to fail even though it described one specific bug. The current form focuses on stronger evidence that the scope is unsuitable, such as an umbrella issue, a support question, unresolved design discussion, explicit major core-internal work, or several abandoned contribution attempts.


**Trade-offs**

[What the quoted check gives up. Any one of these is a complete answer: an issue whose
result it changes, a canary you re-ran with `--only`, a case you accept it will miss, or a
stated reason nothing changed elsewhere. "Nothing changed, and here is how I know" earns
the point in full when the reason follows.]
One trade-off is that the current check can accept an issue that is technically difficult as long as the problem itself is clearly bounded. `issue-19` was my canary for this change. Before revising the check it was rejected with `failed: scope-fits`; after the revision I re-ran it with `--only issue-19` and received:

`issue-19  accept  accept  yes`

This means the rubric may accept some performance or concurrency-related work that is harder than a typical first issue, but I chose not to reject an issue only because it contains technically difficult implementation possibilities.


---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

[Answer all three:

1. The issue's fit to your interests and to the time available.
Issue #72 fits my interests because it is a focused Python backend debugging task with a clear expected behavior and an existing test. The issue is estimated at 1–2 hours, so it also seems manageable for a first contribution.

2. What the verdict identified correctly, and what you weighed that the rubric could not.
The verdict correctly identified that the issue is bounded, active, and testable. The expected behavior is clearly stated: verification against a malformed stored hash should return `False` instead of raising `UnknownHashError`. Beyond what the rubric measured, I also preferred this issue because it gives me debugging and testing practice instead of only making a documentation change.

3. The anticipated difficulty in claiming it.]
The anticipated difficulty in claiming it is that another student has already commented that they would like to claim the issue. The Path Review house rule says classmate claim comments do not block the issue for this exercise, which is why my skill accepted it. I will follow the Unit 2 instructions before posting a claim or beginning the contribution.
---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
