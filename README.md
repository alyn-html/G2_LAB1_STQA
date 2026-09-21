# Lab 1: Black-Box Manual Testing (Test Case Design and Bug Reporting)

**Duration:** 1 hour15 minutes  **Work mode:** pairs for testing, individual bug reports

**Application under test:** PyTodo task-creation form at `https://pytodo-lab.onrender.com/`

## Objective

Design and execute a specification-based test suite for a web form whose validation limits are not published, then report the defects you find. You test from observable behavior only. The source code is not available, and you must not try to obtain it.
## Start here

1. Read this page.
2. Read `SPEC.md` to learn how the app should behave.
3. Open the app at `https://pytodo-lab.onrender.com/` and try it.
4. Fill in `TESTING.md` as you test.
5. File bugs from the **Issues** tab.
## Key concepts

Equivalence Partitioning (EP), Boundary Value Analysis (BVA), positive and negative testing, bug lifecycle, bug reproducibility (ISTQB CTFL, Chapter 4).

## Files in this repository

| File | Purpose |
|---|---|
| `SPEC.md` | Visible behavior of the application. This is your test basis. |
| `TESTING.md` | Your test suite. Copy it, fill it in, and commit it. |
| `.github/ISSUE_TEMPLATE/bug_report.md` | Template loaded when you open a new issue. |

## Tasks

1. **Analyse.** Read `SPEC.md`. In the partition table in `TESTING.md`, list the valid and invalid equivalence classes for each field. Then probe the form to find the hidden limits and note the boundaries.
2. **Design and run.** Write at least **12 test cases** covering **at least 3 fields**. Mark each case as **Positive** (valid, in-range input) or **Negative** (invalid, out-of-range, or malformed input). Use the Technique column to state whether EP or BVA produced the case. Run each case and record the Actual Result and Status.
3. **Report.** File **at least 3 bug reports** in this repository's **Issues** tab, one defect per issue, using the template. Each student files their own issues.
4. **Reproduce.** Write steps that a classmate could follow exactly. If you cannot reproduce a bug a second time, record its reproducibility as Sometimes or Once.

## Suggested time budget

| Minutes | Activity |
|---|---|
| 0 to 15 | Lecture: EP, BVA, positive and negative testing |
| 15 to 20 | Bug report anatomy |
| 20 to 75 | Design and execute tests (write a case, run it, record it, repeat) |
| 75 to 95 | File bug reports |
| 95 to 105 | Debrief |

## Rules

- Test only through the web form at the URL above.
- Do not use automated scanners, load tools, or scripts against the server.
- Search existing issues before filing, to avoid duplicates.
- Do not delete or edit other students' issues.

## Deliverables and assessment

1. `TESTING.md` committed to this repository (test suite and partition table).
2. At least 3 GitHub Issues filed from your own account.

| Criterion | Points |
|---|---|
| Test suite coverage (EP and BVA on at least 3 fields, at least 12 cases) | 35 |
| Positive and negative balance, correct labelling | 15 |
| Execution recorded honestly | 15 |
| Bug reports (complete, one bug each, reproducible) | 30 |
| Partition table | 5 |
