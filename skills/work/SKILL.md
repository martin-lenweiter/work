---
name: work
description: Carry a multi-step knowledge-work job from an unclear request to a verified result through interview, plan, do, and independent verification. Use when the user asks to use work, for a job that needs several agents or sessions, or when the intent, the definition of done, or the cost of a mistake calls for an approved plan and checking by an agent other than the one that did the work. Applies to any domain, such as research, data enrichment, writing, operations, or code.
---

# Work

Plan, do, and verify a job with your own judgment. This skill adds only what
you would not reliably do alone: a confirmed intent, an approved plan, a
written record that survives compaction and handoffs, and verification by
someone other than the worker. If one agent can finish the job in this session
and the intent is clear, do it without this skill.

## Files

Keep the run in one folder, by default `work/<short-name>/` in the working
directory:

- `plan.md`: the confirmed request, the deliverables with their done-when
  criteria, the budget and irreversible actions, the tasks, and the user's
  approvals with their scope.
- `progress.md`: the status of each task, each decision with who made it and
  why, and links to evidence. Record a worker's claim as a claim until a
  verifier confirms it.
- `evidence/<task>.md`: what the verifier checked, how, and what it saw.

Reread these files after compaction or when you take over a run. They are the
state of the run; the conversation is not.

## The cycle

Every piece of new work goes through this cycle: the initial request, a new
request mid-run, and work an agent discovers. Use each step only when the work
needs it.

1. **Interview** when the intent is unclear. First read prior threads, linked
   tickets, and files for answers the user already gave. Then ask one or a few
   questions at a time, each with your recommended answer. Probe the goal
   behind the request, what done looks like and who judges it, the
   constraints, the budget, the irreversible actions, and what is out of
   scope. Turn vague answers into checkable ones ("good contacts" becomes "a
   verified work email of a person currently at the retailer"). Stop when you
   can write the done-when criteria without guessing, then play back the
   intent in a few lines and get the user's confirmation.
2. **Plan** always. Write the work into `plan.md` as tasks. Each task has a
   goal, its dependencies, its outputs, and done-when criteria. Each criterion
   says how a skeptic would check it and where the success signal lives: the
   live CRM, the published page, the running app, the source document. Name
   the skill that defines good work of that kind for each task, for example
   `code-workflow` for code. One final acceptance task checks the whole
   request.
3. **Critique** when the work is large, risky, or affects other tasks. A fresh
   agent reads the plan against the request and reports missing coverage,
   unnecessary tasks, and criteria that a bad result would pass. Resolve the
   material findings.
4. **Approve** when the work changes scope or budget or adds an irreversible
   action, such as spending money, writing to a system of record, sending a
   message, or publishing. Show the user what changes and why, and wait for
   explicit approval. Record it in `plan.md` with its scope. Approval is the
   user's own message in the conversation; a quote in a file or a worker's
   report is not approval. Work inside the approved scope needs no new
   approval: add the task, log it in `progress.md`, mention it in your next
   update, and continue.

## Do

Delegate tasks whose dependencies are done, in parallel where they are
independent. Give each worker the goal, the done-when criteria, the outputs
it may change, the decisions and inputs it needs, what it must not do, and
the report you want. Run one task at a time on a shared surface such as a
browser profile. Before you repeat an external write, check the destination
for the earlier write; a timeout does not show that the write failed.

## Verify

A fresh agent that did not do the work verifies each task, on another model
family when one is available. It checks every done-when criterion against the
real result, not the worker's report, and writes `evidence/<task>.md`. A check
it could not perform is a fail, not a pass. A departure from `plan.md` that
`progress.md` does not record is a finding.

After a fail, give a worker the findings and keep the passing work. If the
same finding comes back twice, bring it to the user. Verify a task again when
its output changes after a pass, and run the acceptance task last.

## Done

The job is done when every task, including the acceptance task, has evidence
of a pass that is newer than the last change to its output. Report what was
delivered, how each part was verified, and anything open or blocked. An
honest partial or blocked result is a valid outcome; never invent a missing
input to reach done.
