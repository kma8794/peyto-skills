---
name: java-coding
description: Use before creating, modifying, refactoring, or meaningfully reviewing Java source code, including tests and code snippets. Applies when Java work emerges during debugging or another task, even if the original prompt did not mention Java. Meaningful review includes assessing Java correctness, design, or readability.
---

# Java Coding

We write code once, but read it hundreds of times.

MUST apply these preferences before the first Java edit or substantive Java review, including when that work becomes necessary later in a task. For review-only requests, assess the code without editing it unless the user authorizes changes.

## Low coupling, high cohesion

This is the most important design principle and guides all other coding preferences within the requested scope. Keep related responsibilities together and dependencies between separate parts minimal. Apply it at every level, from methods and classes to modules and services.

## Minimal change

When modifying existing code, MUST change only the lines required for the requested work. DO NOT reformat, refactor, enhance, or add comments unless necessary for the requested change or explicitly requested. The other style preferences do not justify unrelated edits to existing code.

## Small, well-named methods

Within new or necessarily changed code, extract logical steps into small, well-named private methods. Even three lines deserve a separate method if they form a coherent operation with a meaningful name. Let method names explain the intent, so the calling method reads as a clear sequence of steps without explanatory comments.

## Minimize comments

- DO NOT add comments that explain what the code is doing. Let the code express that clearly.
- Comments are rare and important. Use them only to explain WHY something is done in non-obvious cases or to highlight tricky details a reader might miss.
- Prefer clearer names and code structure over adding an explanatory comment.

## Prefer single lines

MUST keep expressions, statements, and declarations on a single line unless the line exceeds 240 characters. This includes method signatures and their parameter lists: wrap them only when the full line exceeds 240 characters. Stream pipelines and builder chains are exceptions and may span multiple lines even below this limit. This rule does not authorize reformatting untouched code.

## Examples

When deciding whether to wrap a long argument list, consult [good code](references/good-code.md) for the preferred pattern and [bad code](references/bad-code.md) for the pattern to avoid. Other tasks do not require loading these examples.
