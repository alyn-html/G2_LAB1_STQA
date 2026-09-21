# Test Suite: PyTodo Task-Creation Form

Testers (pair): <name 1>, <name 2>
Date: <date>
Application URL: https://pytodo-lab.onrender.com/
Browser and OS: <e.g. Chrome 128 on Windows 11>

## 1. Partition table

Fill one row per field after reading `SPEC.md` and probing the form.

| Field | Valid classes | Invalid classes | Boundary values tested |
|---|---|---|---|
| Title | | | |
| Description | | | |
| Priority | | | |
| Due date | | | |
| Estimated hours | | | |

## 2. Test cases

Type: **Positive** = valid, in-range input. **Negative** = invalid, out-of-range, or malformed input.
Technique: **EP** or **BVA**.
Status: **Pass** (actual matches expected) or **Fail** (mismatch, candidate bug).
Use a valid value for every field you are not testing.

| ID | Type | Technique | Description | Test Data | Expected Result | Actual Result | Status |
|---|---|---|---|---|---|---|---|
| TC-01 | Positive | EP | All fields valid, typical values | Title `Write report`, Priority `3`, Due tomorrow, Hours `2.5` | Task created | | |
| TC-02 | Negative | EP | Required field empty | Title empty, other fields valid | Task not created, message names Title | | |
| TC-03 | Negative | EP | Non-numeric priority | Priority `abc` | Task not created, message names Priority | | |
| TC-04 | | | | | | | |
| TC-05 | | | | | | | |

Add rows until you have at least 12 cases covering at least 3 fields.

## 3. Bugs found

| Issue link | Linked test case | Short title | Severity |
|---|---|---|---|
| | | | |
