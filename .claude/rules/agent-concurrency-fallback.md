# Agent Concurrency Fallback Protocol

> Core principle: Completing the task > pursuing concurrent speed.
> 429 rate limit = concurrency capability revoked. Switch strategy immediately, don't wait.

---

## The Problem

Concurrent Agent calls (multiple Agent tool_use in one message) consume API quota rapidly. When quota is insufficient:
- All concurrent Agents return 429 simultaneously
- Retry = consume quota again = 429 again (vicious cycle)
- **An entire conversation turn wasted with zero output**

This is an **execution strategy error**, not a technical failure. Waiting to retry = banging into the same wall with the same wrong strategy.

---

## Fallback Protocol (3 Steps, Mandatory)

### Step 1: Detect the Signal

Trigger fallback immediately when any Agent returns:

| Signal | Symptom |
|--------|---------|
| HTTP 429 | "rate limit" / "too many requests" |
| Agent timeout | >30 seconds with no response |
| Partial failure | Any one of multiple concurrent Agents errors |

### Step 2: Immediate Fallback (Zero Wait)

**In the same response turn:**
1. **Abandon** all unreturned Agent calls (don't wait, don't retry)
2. **Switch** to sequential direct tool calls (Read / Grep / Bash / Write)
3. **Maintain** the same task goal -- only the execution method changes

```
FAILED (concurrent):
  Agent(A) + Agent(B) + Agent(C) -> all 429

FALLBACK (switch immediately):
  Direct Read A -> Direct Grep B -> Direct Bash C
  (Sequential, stable, reliable)
```

### Step 3: Record

Before conversation ends:
1. Note in audit output: "Concurrency fallback: Agent 429 -> sequential direct calls"
2. Record the fallback event in session notes

---

## Iron Rules

| Rule | Content | Violation Cost |
|------|---------|---------------|
| **No retry** | After 429, do not call Agent again in this response | Retry = waste another turn |
| **No waiting** | Do not output "waiting to retry" or "try again later" | Waiting = user sees AI doing nothing |
| **No quality drop** | Still complete the original task after fallback | Fallback = method change, not standard change |
| **No hiding** | Honestly report fallback events | Hiding = dishonesty |

---

## Decision Tree (Before Every Concurrent Agent Attempt)

```
Need multiple information sources?
  +-- Small volume (<50 lines each) -> Sequential Read directly, skip Agents
  +-- Medium volume -> One Agent (Explore) + direct tool assists
  +-- Large volume, genuinely needs parallelism -> Try concurrent Agents
       +-- All succeed -> Continue normally
       +-- Any returns 429 -> IMMEDIATELY fall back to sequential calls
```

**Key judgment**: Most info-gathering tasks complete in 3-5 sequential direct calls. Only true cross-directory large-scale scans need Agent concurrency.

---

## Cognitive Science Support

| Mechanism | Application |
|-----------|-------------|
| **Sunk Cost Fallacy** | "Already waited, wait more" = trap. "No waiting" rule cuts this |
| **Planning Fallacy** | "Everything will work" = overoptimism. Decision tree forces failure-scenario thinking |
| **Law of the Instrument** | "Have hammer, everything is nail." Decision tree prevents Agent-dependency |
| **Cognitive Flexibility** | Fallback = rapidly switching strategy when environment changes (rate limit) |
| **Occam's Razor** | Sequential calls are the simpler path. Fallback = returning to simplicity when complexity fails |
