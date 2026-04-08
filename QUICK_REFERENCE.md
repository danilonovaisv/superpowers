# Superpowers Skills - Quick Reference Guide

## 🚀 Core Development Workflow

```
Brainstorm → Plan → Worktree → Develop (TDD + Reviews) → Verify → Finish
```

---

## 📋 Skills Cheat Sheet

### 1️⃣ Test-Driven Development (TDD)
**Trigger:** Writing any code  
**Command:** "Use TDD for this feature"

**Cycle:**
1. Write failing test ✗
2. Watch it fail (verify)
3. Write minimal code ✓
4. Watch it pass (verify)
5. Refactor (keep green)
6. Repeat

**Key Rule:** NO CODE WITHOUT FAILING TEST FIRST

---

### 2️⃣ Systematic Debugging
**Trigger:** Any bug or error  
**Command:** "Debug this systematically"

**4 Phases:**
1. **Root Cause Investigation** - Read errors, reproduce, gather evidence
2. **Pattern Analysis** - Find working examples, compare
3. **Hypothesis Testing** - Form theory, test minimally
4. **Implementation** - Create test, fix, verify

**Key Rule:** NO FIXES WITHOUT ROOT CAUSE FIRST

---

### 3️⃣ Writing Plans
**Trigger:** Multi-step feature  
**Command:** "Create implementation plan"

**Structure:**
- Header with goal/architecture/tech stack
- File structure mapping
- Bite-sized tasks (2-5 min each)
- Complete code in every step
- Exact commands and file paths

**Save to:** `docs/superpowers/plans/YYYY-MM-DD-feature.md`

---

### 4️⃣ Subagent-Driven Development
**Trigger:** Executing approved plan  
**Command:** "Execute plan with subagents"

**Process:**
1. Extract all tasks from plan
2. For each task:
   - Dispatch implementer subagent
   - Spec compliance review
   - Code quality review
   - Mark complete
3. Final code review
4. Finish branch

**Key:** Fresh subagent per task + two-stage review

---

### 5️⃣ Verification Before Completion
**Trigger:** Claiming task done  
**Command:** "Verify this is complete"

**Checklist:**
```bash
npm test          # All tests pass?
npm run build     # Build succeeds?
npm run lint      # Clean lint?
```

**Key Rule:** EVIDENCE BEFORE CLAIMS

---

### 6️⃣ Using Git Worktrees
**Trigger:** Starting new work  
**Command:** "Create worktree for this feature"

**Setup:**
```bash
git worktree add ../prompt-app-feature -b feature/name
cd ../prompt-app-feature
npm install
npm test  # Verify clean
```

**Key Rule:** NEVER WORK ON MAIN/MASTER

---

### 7️⃣ Finishing Development Branch
**Trigger:** Work complete  
**Command:** "Finish this branch"

**Steps:**
1. Verify all tests pass
2. Run build
3. Check lint
4. Review changes
5. Present options: Merge/PR/Keep/Discard
6. Execute choice
7. Clean up worktree

**Key Rule:** VERIFIED + MERGED/DISCARDED + CLEANED = FINISHED

---

## 🎯 When to Use Each Skill

| Situation | Skill |
|-----------|-------|
| Starting new feature | `using-git-worktrees` → `writing-plans` |
| Writing code | `test-driven-development` |
| Encountering bug | `systematic-debugging` |
| Executing plan | `subagent-driven-development` |
| Task supposedly done | `verification-before-completion` |
| Feature complete | `finishing-a-development-branch` |

---

## ⚡ Quick Commands

### Start New Feature
```bash
git worktree add ../prompt-app-new-feature -b feature/new-feature
cd ../prompt-app-new-feature
npm install
npm test
```

### Run All Verifications
```bash
npm test && npm run build && npm run lint
```

### Clean Up Worktree
```bash
git worktree remove ../prompt-app-feature-name
git branch -d feature/feature-name
```

---

## 🚩 Red Flags (STOP!)

- ❌ Writing code before test
- ❌ Fixing bug without root cause
- ❌ Skipping verification steps
- ❌ Working on main/master branch
- ❌ Claiming done without evidence
- ❌ Leaving branches unfinished

---

## ✅ Quality Gates

Every change must pass:
1. ✓ Tests written first (TDD)
2. ✓ Spec compliance review
3. ✓ Code quality review
4. ✓ All tests passing
5. ✓ Build successful
6. ✓ Lint clean
7. ✓ Human approval

---

## 📚 Further Reading

- Full skill docs: `.agent/skills/superpowers/skills/*/SKILL.md`
- Implementation summary: `.agent/skills/superpowers/IMPLEMENTATION_SUMMARY.md`
- Original project: https://github.com/obra/superpowers

---

**Tip:** Skills trigger automatically based on context, but you can explicitly request them!
