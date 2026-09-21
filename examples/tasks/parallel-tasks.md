# Splitting one request into parallel tasks

OpenAI's June 2026 knowledge-work report notes that users increasingly run several Codex tasks at the same time. That only works when the tasks are independent. This file shows how to cut a request such as prepare the QUARTER update into pieces.

## Step 1: list the outputs

- Numbers: a table of KEY_METRICS for QUARTER compared with PREVIOUS_QUARTER.
- Narrative: a one-page written update following the structure of LAST_UPDATE_FILE.
- Deck: a slide skeleton with one slide per section of the narrative.

## Step 2: check dependencies

Two tasks can run at the same time only if neither needs the other's output to start.

- Numbers needs only the data source DATA_SOURCE. Independent.
- Narrative needs the structure of LAST_UPDATE_FILE, not the new numbers. Independent, if it leaves placeholders for figures.
- Deck needs the section list, which is known from LAST_UPDATE_FILE. Independent, if it leaves placeholders for figures.
- Final merge needs all three. Runs last.

## Step 3: write one brief per task

Task A (numbers)

    Compute KEY_METRICS for QUARTER and PREVIOUS_QUARTER from DATA_SOURCE.
    Output a table with metric, current, previous, change. State assumptions.

Task B (narrative)

    Draft a one-page update using the section headings from LAST_UPDATE_FILE.
    Where a figure belongs, write the placeholder {{METRIC_NAME}} instead of a number.

Task C (deck)

    Create a slide skeleton with one slide per section heading in LAST_UPDATE_FILE.
    Title and three bullet placeholders per slide, no numbers.

Task D (merge, after A, B and C)

    Replace every {{METRIC_NAME}} placeholder in the narrative and the deck with the
    value from the table in Task A. List any placeholder that had no matching metric.

## Step 4: definition of done for the whole request

No placeholders remain, every number in the narrative and deck matches the table, and the assumptions from Task A are appended to the narrative.
