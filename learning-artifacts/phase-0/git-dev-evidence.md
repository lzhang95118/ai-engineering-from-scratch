# Phase 0 Evidence - Git and Dev Setup

## Objective
Record concrete proof that setup and collaboration basics are working.

## Evidence Checklist
- [x] Git remotes verified (origin and upstream)
- [x] Branch tracking verified
- [x] Local and remote divergence checked
- [x] Sync flow executed end-to-end
- [x] Push path verified
- [ ] Environment basics verified (Python, Node, package tools)

## Run 001
- Date: 2026-11-04
- Context: recover repo state, align with upstream, and verify fork sync path
- Commands executed:
  - git status -sb
  - git remote -v
  - git branch -vv
  - git fetch upstream
  - git checkout main
  - git merge --ff-only upstream/main
  - git push origin main
  - git checkout my-progress
  - git merge main
  - git push origin my-progress
- Output summary:
  - main vs upstream/main: 0 0
  - my-progress vs upstream/main: 0 0
  - my-progress vs origin/my-progress: 0 0
  - push probe returned up-to-date
- Issues found:
  - Temporary push rejection due to workflow permission scope on OAuth token.
- Fix applied:
  - Re-auth and retry push flow, then verify divergence counts.
- Final state:
  - Repository synchronized and clean on tracked branches.

## Gap Drill: Status Commands
Question: when to use short status vs full status?
- short status usage: fast branch/divergence and changed-file glance during sync loop
- full status usage: detailed guidance when staging/unstaging or recovering work
- one real example you observed: used short status for repeated sync checks and full status when diagnosing untracked duplicate files

## Sign-off
- Self-assessment (0-2): 2
  - 0 = unclear
  - 1 = can execute with notes
  - 2 = can execute from memory
- Next target: verify Python/Node toolchain and complete full Phase 0 environment checklist
