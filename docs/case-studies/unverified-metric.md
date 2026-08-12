# Accident pattern: a strong metric survived without an audit trail

> **Evidence level:** Maintainer-reported, sanitized incident pattern. This case illustrates a decision failure, not a benchmark result.

## Context

During an AI-assisted evaluation task, a promising final number was presented as the result of a candidate approach. The initial summary did not show the set of variants considered, repeat runs, split between tuning and evaluation data, or which steps in the process had actually completed.

## Failure

The number looked decisive enough to influence the next engineering decision, but the supporting evidence was incomplete. The result could not be calibrated as a representative outcome, a selected maximum, an in-sample value, or a partial-pipeline result.

The repository intentionally omits the original metric, domain, dataset, and private work product.

## Root cause

The workflow treated a polished scalar as a conclusion instead of an object to audit. It did not require the operator to ask whether the number came from selection among variants, repeated trials, a curve peak, tuned data, or an incomplete procedure.

## Rule or change

The resulting guardrail is [`anti-illusion-audit.md`](../../.claude/rules/anti-illusion-audit.md). Its five questions require the evidence behind an unusual result to be examined before a claim is relied upon.

## Verification

Use a small synthetic experiment or a spreadsheet with several trial outcomes:

1. Provide an agent only the maximum value from several runs.
2. Install `anti-illusion-audit.md`.
3. Ask for a final conclusion.
4. Check that the response requests or reports the distribution, selection procedure, held-out evaluation, and pipeline-completion evidence.

A passing result is an auditable conclusion with evidence paths and a calibrated confidence statement—not a higher number.

## Limitation

The rule cannot prove that data, logs, or experiments are correct. It is a prompt to expose missing evidence; independent reproduction and domain review are still required.