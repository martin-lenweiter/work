# work

`work` is one agent skill that carries a multi-step knowledge-work job from an
unclear request to a verified result. It works in any agent environment that
loads skills, such as Claude Code or Codex, and in any domain: research, data
enrichment, writing, operations, or code.

It adds only what a capable model does not reliably do alone:

1. **A confirmed intent.** When a request is unclear, the agent interviews you
   until it can write the definition of done without guessing.
2. **An approved plan.** Changes to scope, budget, or irreversible actions
   (spending, writing to a system of record, sending, publishing) need your
   explicit approval.
3. **A written record.** Three files hold the state of the run, so any agent
   can resume after compaction or a handoff.
4. **Independent verification.** A fresh agent that did not do the work checks
   each result against the real target, not the worker's report.

## Using it

Open a chat in the folder you want to work in and say:

> Use work to find 50 US retailers that match our criteria and enrich their buyers.

The agent interviews you if needed, writes a plan, has it critiqued when the
job is large or risky, asks for your approval, delegates the tasks, has fresh
agents verify them, and reports done only when every task has evidence of a
pass.

## The run folder

| File | Contents |
|---|---|
| `plan.md` | The confirmed request, the deliverables with done-when criteria, the budget and irreversible actions, the tasks, and your approvals |
| `progress.md` | Task status, decisions with who made them, links to evidence |
| `evidence/<task>.md` | What the verifier checked, how, and what it saw |

## Design principle

The model chooses the approach, the task split, the checks, and the models.
The skill fixes only the parts where a model's own word is not enough: your
intent, your approval, and verification by someone other than the worker.
There is no CLI. Add a mechanical check only when runs show an agent breaking
one of these rules.

Domain rules belong in domain skills, which a plan names per task, for example
a code-workflow skill for software changes.

## Setup

Link `skills/work` into your agent's skills folder.
