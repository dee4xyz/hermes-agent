# Use cases beyond documentation

STE was built for aircraft maintenance manuals. The same properties — one meaning per word, short sentences, condition-first commands — transfer to any text where misreading has a cost. By the end of Issue 8, 64% of registered STE users were outside aerospace and defense.

Each case below names the mode and the adaptations.

## Error messages and CLI output

Mode: procedural. This is the highest-value target: an error message is a 2 a.m. instruction to a stressed reader.

Pattern: state what happened (past simple), state the cause if known, give the command or condition to fix it.

> **Before:** Oops! Something went wrong while attempting to establish a connection. Please ensure your credentials are properly configured and try again.
> **After:** The connection failed. Make sure that the credentials are configured correctly, then try again.

Name a database, user, setting, or failure cause only when the error evidence identifies it.

## Runbooks and standard operating procedures

Mode: strict-leaning procedural. This is STE's home turf — an on-call runbook is a maintenance manual.

- Every step imperative, one instruction per step, conditions first.
- Warnings before the step, command first, risk second.
- 20-word limit enforced hard: an operator under pager stress reads each sentence once.

## Incident reports and postmortems

Mode: descriptive. Simple past only — a timeline in present perfect ("we have identified...") hides when things happened.

> **Before:** We have identified an issue that may have impacted some users' ability to access the service.
> **After:** We identified an issue. Its effect on access to the service is not confirmed.

State known events and retain uncertainty about the rest. Add time ranges, percentages, or causes only when source evidence supports them.

## Commit messages and PR descriptions

Mode: descriptive body, imperative subject. Convention already matches STE: imperative subject line, plain past facts in the body. Apply the substitution table and the 25-word limit to the body. Replace "this PR aims to" with the verified change when possible. Keep intended behavior separate from proven results.

## API changelogs and release notes

Mode: descriptive. One entry, one change, one sentence where possible. "Breaking:" entries follow the warning pattern — command first: "Update your calls to `v2/users`. The `name` field split into `first_name` and `last_name`."

## Instructions for AI agents (prompts, AGENTS.md, skills)

Mode: procedural. A system prompt is a procedure executed by a reader with no ability to ask questions — the exact reader STE was designed for.

- One instruction per sentence keeps rules independently quotable and hard to half-follow.
- One word, one meaning prevents the model from treating "check", "verify", and "validate" as three different operations.
- Condition-first ("If the build fails, stop") beats trailing conditions, which models drop.
- Use "must" for requirements. Keep recommendations optional and label them clearly. Do not change the strength of a rule during a style edit.

## Support macros and status-page updates

Mode: descriptive, 25-word limit. State the verified impact and the next known step. Do not replace an apology with invented outage durations, data-retention claims, or recovery promises.

## Translation and localization prep

Mode: strict. STE's original purpose was making English readable for non-native maintenance crews, and it doubles as pre-editing for machine translation. One meaning per word plus complete grammar (articles, "that") removes most translation ambiguity. If your docs get localized, STE cuts the error rate and the cost.

## UI copy and empty states

Mode: procedural, hard length limits. Buttons and labels are technical names (exempt). Body copy follows the rules: "No projects yet. Create a project to start." Nothing else survives at this length anyway.

## Where STE does not fit

Marketing pages, launch posts, blog voice, brand writing. STE deletes persuasion on purpose. Write those in your own voice — then use STE for the docs the landing page links to.
