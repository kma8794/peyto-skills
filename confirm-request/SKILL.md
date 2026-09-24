---
name: confirm-request
description: MUST Use when the user's task starts or ends with a standalone "confirm", "please confirm", "rephrase", or "please rephrase" cue to restate the request before acting, ignoring case and surrounding punctuation.
---

# Confirm Request

Give the user a quick way to check your understanding before taking any meaningful action. Treat a boundary cue such as "Confirm: fix the login bug" or "Fix the login bug. Please confirm." as a request for this checkpoint, not authorization to execute the task.

MUST use only the request and context already in the conversation. DO NOT investigate or start the requested work: no repository inspection, searches, commands, edits, or delegation to perform the task.

MUST reply in this form:

request: <the user's request, cleaned up and rephrased>

Preserve the request's substance, level of detail, and stated boundaries. Clean up repetition, filler, and unfinished phrasing, especially from voice input. Do not compress away meaningful details or expand the request with invented requirements. Do not add a goal/scope/assumptions/uncertainties template or a routine confirmation question.

Add a separate `need to confirm:` section only when the available context reveals a serious risk or gap, a serious uncertainty about the user's goal, or an important misunderstanding of the context by the user. State the issue plainly and ask only what is needed to resolve it. Omit the section for routine uncertainty or when there is nothing substantial to clarify.

Proceed only after the user explicitly confirms the restated request. If the user corrects it without authorizing execution, update the restatement.
