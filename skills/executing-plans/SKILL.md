---
name: executing-plans
description: Use when partner provides a complete implementation plan to execute in controlled batches with review checkpoints - loads plan, reviews critically, executes tasks in batches, reports for review between batches
---

# Executing Plans

## Overview

Load plan, review critically, execute tasks in batches, report for review between batches.

**Core principle:** Batch execution with checkpoints for architect review.

**Announce at start:** "I'm using the executing-plans skill to implement this plan."

## The Process

### Step 1: Load and Review Plan
1. Read plan file
2. **Review critically** - identify any questions or concerns:
   - Does implementation match stated architecture?
   - Are there contradictions in the plan?
   - Are all dependencies compatible?
   - Are there ambiguous design decisions that need clarification?
3. If concerns: Raise them with your human partner before starting
4. If no concerns: Create TodoWrite and proceed

### Step 2: Execute Batch
**Default: First 3 tasks**

For each task:
1. Mark as in_progress
2. Follow each step exactly (plan has bite-sized steps)
3. Run verifications as specified
4. Mark as completed

#### When Using Subagents

If delegating tasks to subagents, include these **CRITICAL CONSTRAINTS** in every subagent prompt:

```
**CRITICAL ARCHITECTURAL CONSTRAINTS:**

DO NOT make architectural decisions beyond what's explicitly specified in the plan.

If you encounter architectural contradictions, missing implementation details requiring design choices, or dependency conflicts:

STOP immediately and report back with:
1. What you discovered
2. What decision needs to be made
3. Options you identified (with trade-offs)

DO NOT proceed by making assumptions or changing the fundamental architecture.
```

#### Verification Checklist

Before marking a task as completed, verify:

- ✅ Implementation matches planned architecture
- ✅ No unexpected external dependencies added
- ✅ Tests pass as expected
- ✅ No architectural deviations were made

**If any verification fails:** Do not mark complete. Report the issue and get clarification.

### Step 3: Report
When batch complete:
- Show what was implemented
- Show verification output
- Say: "Ready for feedback."

### Step 4: Continue
Based on feedback:
- Apply changes if needed
- Execute next batch
- Repeat until complete

### Step 5: Complete Development

After all tasks complete and verified:
- Announce: "I'm using the finishing-a-development-branch skill to complete this work."
- **REQUIRED SUB-SKILL:** Use superpowers:finishing-a-development-branch
- Follow that skill to verify tests, present options, execute choice

## When to Stop and Ask for Help

**STOP executing immediately when:**
- Hit a blocker mid-batch (missing dependency, test fails, instruction unclear)
- Plan has critical gaps preventing starting
- You don't understand an instruction
- Verification fails repeatedly

**Ask for clarification rather than guessing.**

**Examples of when to STOP:**
- Plan's implementation contradicts stated architecture
- Dependencies conflict with plan specifications
- Implementation requires services not mentioned in plan
- Subagent reports it cannot proceed without architectural guidance

## When to Revisit Earlier Steps

**Return to Review (Step 1) when:**
- Partner updates the plan based on your feedback
- Fundamental approach needs rethinking

**Don't force through blockers** - stop and ask.

## Remember
- Review plan critically first
- Follow plan steps exactly
- Don't skip verifications
- Reference skills when plan says to
- Between batches: just report and wait
- Stop when blocked, don't guess
