# Task: PULL_REQUEST_TITLE

Paste everything below this line as the task. Replace ALL_CAPS placeholders first.

---

## Goal

Fix ISSUE_DESCRIPTION in REPOSITORY_NAME. The bug shows up when STEPS_TO_REPRODUCE.
Expected behaviour: EXPECTED_BEHAVIOUR. Current behaviour: CURRENT_BEHAVIOUR.

## Context

- The relevant code lives under PATH_TO_MODULE.
- Tests for this area are in PATH_TO_TESTS and run with TEST_COMMAND.
- Coding conventions: follow the style of the surrounding files; do not reformat code you did not change.

## Constraints

- Keep the change limited to the files that need it.
- Do not change public interfaces, dependency versions or configuration files.
- Do not delete or skip existing tests to make the suite pass.
- If the fix needs a decision I have not covered, stop and ask instead of guessing.

## Definition of done

1. The bug can no longer be reproduced with the steps above.
2. A test that fails before the change and passes after it is added or updated.
3. TEST_COMMAND passes.
4. A short summary (five lines or fewer) explains what changed and why, ready to paste into the pull request description.
