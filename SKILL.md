---
name: brain-harvest
description: >-
  Inspects files modified in the current session, recent git changes, and conversation history,
  identifies unrecorded architectural decisions, bugfixes, configs, or patterns, checks them
  against your Second Brain, and reports documented vs missing memories with a 1-click save bundle.
---

# Brain Harvest — Session Knowledge Gap Detector (`/brain-harvest`)

Use this skill when you want to audit your current session's work to ensure nothing important was forgotten before closing the IDE or ending a session.

---

## What Happens When Invoked

When `/brain-harvest` is triggered, execute this 4-step workflow:

### Step 1: Inventory Session Changes
1. Check `git status` and `git diff --stat` (if in a git repository) to identify all modified, created, or deleted files in the workspace.
2. If not a git repo or no git changes, inspect the files read or written during this conversation and scan recent conversation turns.
3. Extract key technical facts:
   - Architectural decisions (e.g. chosen libraries, protocols, ports, data schemas)
   - Fixed bugs and their root causes (e.g. why an audio glitch occurred and how it was fixed)
   - Configuration adjustments (e.g. settings keys, environment constraints)
   - Reusable patterns or scripts created

### Step 2: Query Second Brain for Existing Coverage
For each extracted item, run an intent-framed `recall` query against the `second-brain` MCP server:
- Example: `"User is checking documentation for [topic/decision] in [project]"`

### Step 3: Classify and Build Gap Report
Separate findings into three clear sections:
1. 🟢 **Already Covered**: Changes or decisions that already have a corresponding memory in Second Brain (display matching Memory ID and snippet).
2. 🟡 **Gaps Detected (Unrecorded)**: Key decisions, fixes, or configurations discovered in the session files that are NOT found in the Second Brain.
3. 📋 **Ready-to-Save Bundle**: Pre-formatted commands for every gap found, complete with suggested `#tags` and volatility (`!durable` for permanent rules/choices, `!state` for evolving project status).

### Step 4: User Action
Present the report. If the user replies with "save all", "save 1 and 3", or runs the commands directly, execute the saves immediately using `remember`.

---

## Syntax

```
/brain-harvest [optional path or topic filter]
```

## Examples

```
/brain-harvest
/brain-harvest Live Actions
/brain-harvest scripts/
```
