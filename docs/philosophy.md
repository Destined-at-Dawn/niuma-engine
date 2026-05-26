# Design Philosophy

## Three Fundamental Beliefs

### 1. Honesty Determines Value

A high score with a false calibration is a negative asset. Always ask first: "How was this number produced?"

The most dangerous mistake AI makes is not getting things wrong, but confidently giving wrong good results. A "test passed" without a calibration label is more dangerous than an explicit "test failed" -- because it makes you let your guard down.

### 2. Efficiency Comes from Parallelism and Non-Repetition

An unrecorded dead end will be retried by every subsequent conversation.

AI's context is limited. A "this path doesn't work" verified in the previous session is completely unknown to the next one. Archive once = all future sessions save that cost.

### 3. Boundary Awareness

A mature delivery is not "everything is done," but accurately knowing what was achieved and what cannot be claimed.

Every deliverable comes with a three-column boundary checklist: verifiable material (with complete evidence), non-verifiable material (insufficient calibration), and claims not yet supportable (speculation).

## Why Engineering Discipline is Needed

AI agents are good at executing instructions, but not at:
- Questioning their own output
- Remembering which paths don't work
- Saying "I'm not sure" when uncertain
- Distinguishing "looks good" from "is actually good"

niuma-engine fills these gaps.

## Relationship with Human Engineering Practices

The laws of niuma-engine are not AI-specific -- they come from human engineering practices:
- Evidence layering -> Scientific method's reproducibility
- Anti-illusion audit -> Statistics' multiple comparison correction
- Negative result archiving -> Laboratory notebook tradition
- Gate culture -> CI/CD pipelines

AI needs these because it is more prone than humans to the habit of "making mistakes with confidence."
