---
name: orchestrate
description: Use when work should be delegated across subagents while one orchestrator keeps decisions, scope, integration, and final acceptance.
---

# Orchestrate

The orchestrator owns task understanding, product and architecture decisions, decomposition, integration, and final acceptance. Subagents handle bounded research, implementation, testing, and review. The orchestrator does not duplicate their mechanical work.

## Workflow

1. Read the request and applicable repository instructions. Resolve decisions that affect scope, behavior, architecture, or public interfaces.
2. Split the work into bounded packages. Run independent packages concurrently and dependent work sequentially. For a small task, use one worker and a proportional check.
3. Prevent concurrent writers from touching the same files, tests, schemas, generated artifacts, or shared configuration. Assign exact ownership or serialize the work.
4. Dispatch each package with the objective, allowed scope and ownership, acceptance criteria, required checks, non-goals, permission limits, and expected evidence.
5. Receive results through native messages. A HANDOFF reports the result, changed files or findings, checks run, acceptance mapping, risks, and next step.
6. Inspect the actual evidence and integrated result. `DONE` is a claim, not proof.
7. Return defects to the responsible implementer. Use a fresh independent reviewer when the work has meaningful behavioral, integration, security, or regression risk.
8. Synthesize the final answer only after the accepted result is verified.

Keep coordination in messages and HANDOFF replies. Do not create plans, state files, task files, logs, or other coordination artifacts unless the user or repository contract explicitly requires them.

When TDD is requested, establish accepted behavior and an exact observable boundary first. A tester demonstrates a meaningful RED before implementation; an implementer produces the smallest GREEN result; a fresh reviewer verifies the behavior and test quality. Tests written after existing implementation are regression tests, not TDD. Never delete or revert existing work without authorization.

Invocation authorizes delegation inside the requested task. It does not authorize expanded scope, commits, pushes, deployments, publication, destructive changes, or messages to people or services outside the run. Preserve existing permission boundaries. If delegation is unavailable or conflicts with another instruction, state the conflict before taking over delegated work.

## Model routing

Roles matter more than model names. Use the user's routing when specified. Otherwise, when these Codex models are available:

- The current capable model remains the orchestrator; Astra is one strong option.
- Prefer Luna for inexpensive search, context gathering, and bounded checks.
- Prefer Terra for code implementation, UI work, and local implementation decisions.
- Use a fresh suitable agent for independent review; Sol is one option.

Adapt to the available models, task, cost, and observed results. Do not claim that routing is automatic or universally optimal.
