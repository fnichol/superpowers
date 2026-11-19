# When a Finding Would Change the Plan

Part of superpowers:subagent-driven-development and superpowers:executing-plans.

**The accepted plan is not yours to change.** This overrides "Rulings, not
stalls" and the four-stop limit in SKILL.md. Your human partner accepted this
plan and the spec it argues from. Rulings cover only the choices the plan
deliberately leaves to the implementer: a function body, a library call, a
local name, a test helper. They never cover the plan itself.

A fifth thing stops you: any finding whose resolution would change, skip,
reorder, reinterpret, or work around what the plan or spec says. That
includes a step that contradicts the spec or the stated architecture, tasks
whose interfaces don't line up, a dependency or service the plan doesn't
name, a command that cannot work as written, and a review fix that can't be
made without departing from the plan. When one comes up:

1. Stop before writing anything that depends on the answer. Leave
   committed work as it is.
2. Write `Task <N>: STOPPED: <finding>` to the ledger, so a resumed session
   cannot continue past it.
3. Tell your human partner what you found, what decision it needs, and the
   options you see, with their trade-offs and your recommendation.
4. Wait. Resume only after they decide and the plan (and the spec, if it is
   affected) has been updated to match. Then write
   `Task <N>: RESOLVED: <decision> — plan updated` to the ledger, re-read
   the updated task, and continue from the ledger.

A `Ruling:` that changes the plan is a decision made without your partner,
however it is labeled.
