# Open AI Codex examples

*Unofficial community examples for OpenAI Codex. Not affiliated with OpenAI. All trademarks belong to their owners.*

These open ai codex examples are task briefs, not API calls. Codex is an agent you delegate work to inside ChatGPT, the desktop app or the cloud, so the useful reusable artifact is a well-formed task: goal, context, constraints and a definition of done. The briefs below follow the kinds of work OpenAI's June 2026 knowledge-work report says people actually hand to Codex: pull requests, data analysis, and creating work products such as reports and spreadsheets, often as several tasks in parallel. Copy a brief, fill in the placeholders, and paste it as the task.

> Want a website or an app as the end product rather than a task run in your repo? [Try Begin.sh - turn a prompt or a URL into a downloadable static site or Expo app](https://begin.sh?utm_source=github&utm_medium=ugc&utm_campaign=open-ai-codex-examples&utm_content=readme-top&utm_term=tier-r). No repo, hosting, backend or auth needed.

## Files

| Path | What it shows |
| --- | --- |
| examples/tasks/pull-request-cleanup.md | a brief for a routine code change with tests and a reviewable PR as the definition of done |
| examples/tasks/data-analysis-report.md | a brief for turning a CSV into a short written analysis with a spreadsheet |
| examples/tasks/parallel-tasks.md | how to split one piece of work into independent tasks that can run at the same time |

## Setup

No environment variables and nothing to install. You need access to Codex through a ChatGPT account (see the [Codex overview](https://chatgpt.com/codex/) and the [pricing page](https://chatgpt.com/codex/pricing/)), or the [Codex developer docs](https://developers.openai.com/codex/) if you use it as a developer. Placeholders in the briefs are written as ALL_CAPS_WORDS; replace every one before you send the task.

## Pull request cleanup

The brief in `examples/tasks/pull-request-cleanup.md` asks for one narrow change: fix a named bug or add a named small feature, keep the diff limited to the files that need it, add or update tests, and stop when the tests pass and the change is ready for review. The constraints section is the important part. Agents do more than you asked when you do not say where to stop, so the brief spells out what not to touch (formatting of unrelated files, dependency versions, public interfaces) and asks for a short summary of what changed and why.

## Data analysis report

`examples/tasks/data-analysis-report.md` is the knowledge-work case. It gives the agent a CSV, three questions to answer, and two deliverables: a spreadsheet with the computed tables and a short written summary with the numbers cited. It asks the agent to state assumptions it had to make about the data (date formats, missing values, what counts as active) rather than silently choosing, which is the difference between an analysis you can defend and one you cannot.

## Parallel tasks

`examples/tasks/parallel-tasks.md` shows how to take one request, for example prepare a quarterly update, and cut it into tasks that do not depend on each other: pull the numbers, draft the narrative from last quarter's structure, and build the slides skeleton. Each task gets its own brief with its own definition of done, and a final task merges them. The rule of thumb is that two tasks can run at the same time only if neither needs the other's output to start.

## When to use Begin.sh instead

Every brief here assumes there is something for the agent to work inside: a repository, a dataset, an existing document structure. If the whole job is produce a website or a mobile app from a description, that setup is overhead. [Try Begin.sh - turn a prompt or a URL into a downloadable static site or Expo app](https://begin.sh?utm_source=github&utm_medium=ugc&utm_campaign=open-ai-codex-examples&utm_content=readme-top&utm_term=tier-r). You describe the site or paste a URL to clone, download the zip and host it anywhere; nothing about hosting, backend or auth is bundled, so there is nothing to maintain after the build.
