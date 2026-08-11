# Case studies

Case studies are the evidence layer of niuma-engine. A case should explain a real failure pattern without exposing private data, credentials, proprietary source code, or identifiable third parties.

## Case template

```md
# [Short failure-mode title]

## Context
What kind of task and environment was involved? Keep it anonymous and reproducible.

## Failure
What happened, and what was the observable impact?

## Root cause
Why did the existing workflow fail to catch it?

## Rule or change
Which niuma-engine rule was added or changed? Link to the file.

## Verification
How can another maintainer test whether the rule changes the workflow?

## Limitation
What does this rule still not guarantee?
```

Label anecdotal maintainer observations as such. Do not represent them as independently validated results without public evidence.
