---
name: java-coding
description: Apply personal coding preferences when writing or reviewing Java code.
---

# Java Coding

We write code once, but read it hundreds of times.

## Low coupling, high cohesion

This is the most important principle and guides all other coding preferences. Keep related responsibilities together and dependencies between separate parts minimal. Apply it at every level, from methods and classes to modules and services.

## Minimal change

When modifying existing code, change only the lines required to implement the requested feature or fix. Do not reformat, refactor, enhance, or add comments unless necessary for the requested change or explicitly requested. The other style preferences do not justify unrelated edits to existing code.

## Small, well-named methods

Extract logical steps into small, well-named private methods. Even three lines deserve a separate method if they form a coherent operation with a meaningful name. Let method names explain the intent, so the calling method reads as a clear sequence of steps without explanatory comments.

## Minimize comments

- Do not add comments that explain what the code is doing. Let the code express that clearly.
- Comments are rare and important. Use them only to explain WHY something is done in non-obvious cases or to highlight tricky details a reader might miss.
- Prefer clearer names and code structure over adding an explanatory comment.

## Prefer single lines

Keep expressions, statements, and declarations on a single line unless the line exceeds 240 characters. This includes method signatures and their parameter lists: wrap them only when the full line exceeds 240 characters. Stream pipelines and builder chains are exceptions and may span multiple lines even below this limit.

## Examples

When applying these preferences, consult [good code](references/good-code.md) for preferred patterns and [bad code](references/bad-code.md) for patterns to avoid.
