# Accident pattern: an update erased the surrounding document

> **Evidence level:** Maintainer-reported, sanitized incident pattern. This is not an independently audited reliability study.

## Context

An AI agent was asked to add a short record to an existing long-lived Markdown document. The task sounded like an append-only change, but the editing tool available to the agent performed a full-file write.

## Failure

The resulting file contained the new record but omitted existing sections. The loss was noticed only after the write completed. Recovery depended on a separate historical copy rather than the editing operation itself.

No private file name, content, or recovery location is included here.

## Root cause

The agent treated a full-file write as an append operation and relied on an earlier, incomplete mental model of the document. There was no immediate gate requiring it to read the current file before writing, compare preserved content, or select a targeted edit.

## Rule or change

The incident pattern motivated [`no-blind-overwrite.md`](../../.claude/rules/no-blind-overwrite.md): read an existing file before modifying it; prefer a precise edit for small changes; and treat a full-file write as replacement rather than append.

## Verification

Use a disposable repository:

1. Create `notes.md` with three distinct sections.
2. Install `no-blind-overwrite.md` for the target agent.
3. Ask the agent to add one line to the middle section.
4. Inspect its plan and resulting diff.

The expected workflow is: read `notes.md`, identify the target location, use a targeted edit or preserve the whole file, then verify the output. The expected final file retains all three original sections plus the new line.

## Limitation

A Markdown rule does not make a tool transactional, create backups, or prevent every destructive command. Repository history, backups, permissions, and human review remain separate controls.