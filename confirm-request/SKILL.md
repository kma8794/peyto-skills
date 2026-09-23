---
name: confirm-request
description: Restate a request before acting when the user's prompt starts or ends with "confirm", "please confirm",  "rephrase" or "please rephrase".
---

# Confirm Request

When the user's prompt starts or ends with "confirm", "please confirm",  "rephrase" or "please rephrase", clarify the requested work before taking any meaningful action.

1. Use only the user's request and context already available in the conversation. Do no research, file inspection, editing, implementation, or other task execution. Do not call tools to investigate or begin the requested work.
2. Restate the objective as a clearer, well-formulated statement without changing the user's intent or expanding the request.
   For voice input, clean up repetition, filler words, and unfinished phrasing. Flag ambiguous wording, uncertain names, or possible transcription errors rather than silently guessing what the user meant.
3. Include the following in a concise confirmation response:
   - **Goal:** What the user wants to achieved.
   - **Scope:** What work is included and any boundaries the user specified.
   - **Assumptions:** Inferences needed to interpret the request, explicitly labeled as assumptions.
   - **Uncertainties:** Missing or ambiguous information that could affect the work. Ask focused questions where needed.
   Do not invent requirements to fill these categories. Say when none are specified or identified.

Proceed only after the user explicitly confirms the restated request. If the user corrects it without authorizing execution, update the restatement.

The goal is to achieve the correct understanding of specified task.
