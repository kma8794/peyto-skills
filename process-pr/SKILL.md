---
name: process-pr
description: Process existing PR review comments interactively - track feedback in a work log, then explain, discuss, or fix selected items under the user's supervision.
---

# Process PR

The user owns the code and is responsible for reviewing, approving, and merging it. 
The agent helps work through the user's feedback under their supervision. 
This is why the user controls the pace: reviews, pushes, replies, and thread resolution are not automatic.

## The lifecycle

1. **User** opens a PR from a feature branch, self-reviews it, and leaves inline code comments.
2. **Process comments** — fetch them and build the PR work log.
3. **Work the table** one item at a time, under the user's supervision.
4. **Reply to comments** in the original PR when the user explicitly asks.
5. **Strategic review** when the user asks for it.
6. **User merges.** Not our job — do not offer to automate it.

Replies and strategic review can be requested at any point.

## Process comments

Identify the repository and PR from context; ask if ambiguous. Fetch all inline code-comment threads and their replies. General concerns also appear as inline comments; their file location may be incidental. Read the relevant code before classifying feedback.

Reuse the existing PR work log or create `docs/agent/pr-N.md`, following repository conventions. Include the PR URL and a table with:

- Stable item ID, source comment link, file/line, and summary.
- **Action:** `explain`, `discuss`, or `fix`.
- **Status:** `open` or `done`; record explicit deferrals or dismissals separately.

Group replies about the same concern. On refresh, preserve IDs, decisions, and progress; add new concerns without duplicating existing ones.

Present the table and wait for the user to select an item. Intake alone does not authorize fixes.

## Work the table

Handle only the selected item, unless the user requests a batch.

- **Explain:** answer the question using evidence from the code.
- **Discuss:** explain the tradeoffs and recommendation; agree on an approach before editing.
- **Fix:** make the focused change directly. Switch to discussion if a decision is needed.

Assess comments critically; explain disagreements and let the user decide. Check implemented changes before marking them done. Record the outcome, decision, and validation beneath the item's ID. Keep open items above done items without renumbering.

Update the log, report the outcome briefly, and wait for the next selection. Unanswered questions and unfinished changes remain open.

Leave changes uncommitted by default. 
Pushing and merging remain with the user unless explicitly requested. Thread resolution is the user's step, outside this workflow. Local `done` status does not resolve a remote thread.

## Reply to comments

Only when the user explicitly asks, reply to each requested comment separately in its original PR thread. Never post comments without that request.

Posting a reply must leave the thread unresolved. The user resolves threads.

State the actual outcome in very short, plain English. Skip implementation details. Examples:

- Renamed.
- Removed.
- Added additional validation for fields A, B, C.
- As agreed, this is required.
- As agreed, leaving for later refactoring.
- Created separate ticket to address later.
- Reused ItemDetails class.

Use agreement or ticket wording only when that agreement or ticket exists. Record posted replies in the log to avoid duplicates.

## Strategic review

When requested, review the whole PR for gaps, contradictions, unclear decisions, and overlooked consequences against its purpose and project documentation.

Present a short prioritized list. Add actionable findings to the log as open items and wait for selection.
