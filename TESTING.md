# Test Suite: PyTodo Task-Creation Form

Testers (pair): GROUP 2 
1. Alya Nabihah bt Ahmad Kamarzaman (22012109)
2. Mohammad Syarafuddin Bin Mohd Zaidi (22006949)
3. ⁠Nurul Hafizhah Binti Zainal Abidin (22005732)
4. ⁠Muhammad Adam Muzir Bin Mohamad Azmi (22006801)

Date: 21/09/2026

Application URL: https://pytodo-lab.onrender.com/

Browser and OS: Chrome 123 on Windows 11

## 1. Partition table

| Field | Valid classes | Invalid classes | Boundary values tested |
|---|---|---|---|
| Title | Short text with 3–49 characters | Empty; spaces only; 1–2 characters; 50 or more characters | 1, 2, 3, 49, 50 characters |
| Description | Valid text | Empty/invalid input if required | Not specified in SPEC.md / lab file |
| Priority | Whole-number priority within valid range | Non-numeric; 6 or higher; decimal format such as 3.0; explicit positive sign such as +3 | 5, 6, 7 |
| Due date | Today or future calendar date within allowed range | Past date; date more than 1 year in the future | Yesterday, today, 1 year from today, 1 year + 1 day |
| Estimated hours | Positive number with at most one decimal place | Zero/negative; more than allowed range; more than one decimal place; invalid decimal formats | 0.1, 0.4, 0.5, 5.0, maximum valid value |

## 2. Test cases

Type: **Positive** = valid, in-range input. Type: **Negative** = invalid, out-of-range, or malformed input.
Technique: **EP** or **BVA**.
Status: **Pass** (actual matches expected) or **Fail** (mismatch, candidate bug).

| ID | Type | Technique | Description | Test Data | Expected Result | Actual Result | Status |
|---|---|---|---|---|---|---|---|
| TC-01 | Positive | EP | All fields valid, typical values | Title `Write report`, Priority `3`, Due tomorrow, Hours `2.5` | Task created | Task created | Pass |
| TC-02 | Negative | EP | Required Title field is empty | Title empty, other fields valid | Task not created, message names Title | Task not created, Title validation shown | Pass |
| TC-03 | Negative | EP | Title contains only spaces | Title `   `, other fields valid | Task not created, message indicates Title is not valid | Task successfully created | Fail |
| TC-04 | Negative | BVA | Title is below minimum valid length | Title `A`, other fields valid | Task created because short text is valid | Task rejected: Title is not valid | Fail |
| TC-05 | Positive | BVA | Title contains exactly 50 characters | Title = 50 `A`s, other fields valid | Task created | Task rejected: Title is not valid | Fail |
| TC-06 | Negative | EP | Priority contains non-numeric input | Priority `abc`, other fields valid | Task not created, message names Priority | Task not created, Priority validation shown | Pass |
| TC-07 | Negative | BVA | Priority is 6 | Priority `6`, other fields valid | Task rejected because it is outside the intended 1–5 range | Task successfully created | Fail |
| TC-08 | Positive | EP | Priority is a whole number represented as 3.0 | Priority `3.0`, other fields valid | Task created because 3.0 is mathematically a whole number | Task rejected: Priority is not valid | Fail |
| TC-09 | Positive | EP | Priority uses an explicit positive sign | Priority `+3`, other fields valid | Task created because +3 is a valid whole number | Task rejected: Priority is not valid | Fail |
| TC-10 | Negative | EP | Due date is in the past | Due date `2026-09-20`, other fields valid | Task not created, message indicates due date cannot be in the past | Task successfully created | Fail |
| TC-11 | Negative | BVA | Due date is more than one year in the future | Due date `2027-09-22`, other fields valid | Task created because it is a valid future calendar date | Task rejected: Due date is not valid | Fail |
| TC-12 | Positive | BVA | Estimated Hours is at the smallest valid value | Hours `0.1`, other fields valid | Task created | Task rejected: Due date is not valid | Fail |
| TC-13 | Positive | EP | Estimated Hours uses leading decimal format | Hours `.5`, other fields valid | Task created | Task rejected: Due date is not valid | Fail |
| TC-14 | Positive | EP | Estimated Hours uses trailing decimal format | Hours `5.`, other fields valid | Task created | Task rejected: Due date is not valid | Fail |
| TC-15 | Negative | EP | Estimated Hours is out of range | Hours `99`, other fields valid | Task not created, message says Estimated hours is not valid | Task rejected, but message incorrectly says Due date is not valid | Fail |

## 3. Bugs found

| Issue link | Linked test case | Short title | Severity |
|---|---|---|---|
| <GitHub Issue #1> | TC-03 | Title accepts only spaces | Medium |
| <GitHub Issue #2> | TC-04 | Title rejects 1–2 character inputs | Medium |
| <GitHub Issue #3> | TC-05 | Title rejects exactly 50 characters | Medium |
| <GitHub Issue #4> | TC-07 | Priority accepts value 6 | Medium |
| <GitHub Issue #5> | TC-08 | Priority rejects 3.0 | Low |
| <GitHub Issue #6> | TC-09 | Priority rejects +3 | Low |
| <GitHub Issue #7> | TC-10 | Due date accepts past dates | High |
| <GitHub Issue #8> | TC-11 | Due date rejects dates more than 1 year ahead | Medium |
| <GitHub Issue #9> | TC-12 | Estimated Hours rejects 0.1–0.4 | Medium |
| <GitHub Issue #10> | TC-13 | Estimated Hours rejects leading decimal format | Low |
| <GitHub Issue #11> | TC-14 | Estimated Hours rejects trailing decimal format | Low |
| <GitHub Issue #12> | TC-15 | Estimated Hours shows incorrect validation message | Medium |
