---
name: brainstorming
description: Use when creating or developing, before writing code or implementation plans - refines rough ideas into fully-formed designs through collaborative questioning, alternative exploration, and incremental validation. Don't use during clear 'mechanical' processes
---

# Brainstorming Ideas Into Designs

## Overview

Help turn ideas into fully formed designs and specs through natural collaborative dialogue.

Start by understanding the current project context, then ask questions one at a time to refine the idea. Once you understand what you're building, present the design in small sections (200-300 words), checking after each section whether it looks right so far.

**Core principle:** When new information invalidates your approach, going backward is faster than patching forward.

## The Process

**Understanding the idea:**
- Check out the current project state first (files, docs, recent commits)
- Ask questions one at a time to refine the idea
- Prefer multiple choice questions when possible, but open-ended is fine too
- Only one question per message - if a topic needs more exploration, break it into multiple questions
- Present all questions conversationally in natural language - NEVER use AskUserQuestion tool
- "Multiple choice" means conversational options with reasoning, not structured prompts
- Example: "I see three approaches: (1) Redis, (2) in-memory, (3) file-based. I'd lean toward Redis because... Thoughts?"
- Focus on understanding: purpose, constraints, success criteria

**Exploring approaches:**
- Propose 2-3 different approaches with trade-offs
- Present options conversationally with your recommendation and reasoning
- Lead with your recommended option and explain why

**Presenting the design:**
- Once you believe you understand what you're building, present the design
- Break it into sections of 200-300 words
- Ask after each section whether it looks right so far
- Cover: architecture, components, data flow, error handling, testing
- Be ready to go back and clarify if something doesn't make sense

## When to Go Backward

**You can and should revisit earlier steps when:**

- Partner reveals new constraint during exploration or design → Go back to understanding
- Validation shows fundamental gap in what you're building → Go back to asking questions
- Partner questions your approach during design → Go back to exploring alternatives
- Something doesn't make sense → Stop and clarify

**Don't force forward progression when going backward would give better results.**

This is not about being "stuck" - it's about getting clarity before continuing.

### Red Flags - Stop and Go Back

If you catch yourself thinking any of these, STOP and go backward:

- "The architecture stays mostly the same, just swap X for Y"
- "I can adapt what I already presented"
- "Going back wastes the work I've done"
- "It's just a small constraint, I can work around it"

**Reality:** When fundamental constraints change, adapting forward = patching over the wrong approach.

## After the Design

**Documentation:**
- Write the validated design to `docs/plans/YYYY-MM-DD-<topic>-design.md`
- Use elements-of-style:writing-clearly-and-concisely skill if available
- Commit the design document to git

**Implementation (if continuing):**
- Ask: "Ready to set up for implementation?"
- Use superpowers:using-git-worktrees to create isolated workspace
- Use superpowers:writing-plans to create detailed implementation plan

## Key Principles

- **One question at a time** - Don't overwhelm with multiple questions
- **Multiple choice preferred** - Easier to answer than open-ended when possible
- **YAGNI ruthlessly** - Remove unnecessary features from all designs
- **Explore alternatives** - Always propose 2-3 approaches before settling
- **Incremental validation** - Present design in sections, validate each
- **Be flexible** - Go back and clarify when something doesn't make sense
