# Accident pattern: a sub-agent returned an unusable investigation

> **Evidence level:** Maintainer-reported, sanitized incident pattern. The source rule records multiple agent-failure retrospectives; this page generalizes the pattern without exposing private tasks or logs.

## Context

A parent agent delegated an investigation to a sub-agent using a broad request such as “look into the project.” The sub-agent did not have the parent conversation context and received neither a precise result format nor a stopping condition.

## Failure

The sub-agent either searched too broadly, returned a long narrative with no directly usable paths or evidence, or stopped before checking the relevant scope. The parent agent then had to repeat the work or reconstruct the intended task manually.

## Root cause

The delegation assumed that a sub-agent inherited the parent context. In practice, the task lacked three executable elements: a specific objective, an output format, and a stopping condition. Task type was also not matched deliberately to the required work.

## Rule or change

The response is [`agent-prompt-ironclad.md`](../../.claude/rules/agent-prompt-ironclad.md), supported by [`subagent-strategy.md`](../../.claude/rules/subagent-strategy.md). The rules require explicit context, objective, output format, scope, and stop condition before delegation.

## Verification

In a public or disposable codebase, compare two read-only investigations:

1. Delegate “find relevant files” without constraints.
2. Delegate the same task with a directory boundary, exact search terms, output format of `path:line`, and a stop condition.
3. Compare whether the second result is directly actionable and covers the declared scope.

Record the commands, tool version, task scope, and any misses. Do not generalize a single comparison into a universal performance claim.

## Limitation

Well-scoped prompts do not guarantee correct reasoning, complete search results, or suitable model selection. The parent agent must still inspect evidence and make the final decision.