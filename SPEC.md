# PyTodo Task-Creation Form: Behavior Specification

This page describes what a user can observe. It is the test basis for expected results. It does not state numeric limits: finding them is part of the lab.

## Fields

| Field | Required | Description |
|---|---|---|
| Title | Yes | Short text naming the task. |
| Description | No | Longer free text. |
| Priority | Yes | Whole number on a scale from lowest to highest importance. |
| Due date | Yes | Calendar date written as `YYYY-MM-DD`. |
| Estimated hours | Yes | Positive number with at most one decimal place. |

## Rules

1. Every field has limits. Values outside the limits must be rejected.
2. A value made only of spaces counts as blank. A blank required field must be rejected.
3. A due date in the past must be rejected. Dates too far in the future must also be rejected.
4. Title and Description accept any printable text, including non-English characters and emoji.
5. Priority must be a whole number. Decimals, letters, and negative numbers are invalid.
6. Estimated hours must be greater than zero.

## Outcomes

| Situation | Expected behavior |
|---|---|
| All fields valid | The page shows "Task created" with an ID and the saved values. The task appears on the All tasks page. |
| Any field invalid | The page shows "Task not created" and lists a message for each invalid field. No task is saved. |
| Error messages | Each message names the field that is invalid. |
| Any input | The application never shows a server error page. |
