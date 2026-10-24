# Brain Harvest

> **Tri-Platform Agent Skill** for Claude Desktop / Code, Grok CLI, and Google Antigravity / Gemini.  
> Session Diff Gap Analyzer — Inspects session files, git changes, and conversation history, identifies unrecorded architectural decisions or bugfixes, and generates 1-click save bundles.

---

## Overview

`brain-harvest` provides standardized capabilities across conversational AI platforms:
- Session diff gap analysis comparing modified files against Second Brain.
- Identification of unrecorded bugfixes, configurations, and decisions.
- Formatted 1-click /brain-save command bundle for instant gap closure.
- Tri-platform NTFS junctions connecting Claude, Grok, and Antigravity.
- Standard documentation suite: SKILL.md, HOW_TO_USE.txt, IMPLEMENTATION_PLAN.md, and README.md.

---

## Tri-Platform Architecture

Zero duplicate code across platforms. Canonical source resides in `.agents`:
- **Canonical Source**: `C:\Users\<you>\.agents\skills\brain-harvest`
- **Claude**: `C:\Users\<you>\.claude\skills\brain-harvest` (NTFS Junction)
- **Grok**: `C:\Users\<you>\.grok\skills\brain-harvest` (NTFS Junction)
- **Antigravity**: `C:\Users\<you>\.gemini\config\skills\brain-harvest` (NTFS Junction)

---

## Documentation Suite

- [`HOW_TO_USE.txt`](HOW_TO_USE.txt): Standardized user guide and prompt templates.
- [`IMPLEMENTATION_PLAN.md`](IMPLEMENTATION_PLAN.md): Feature checklist and roadmap.
- [`App Changes Tracker.html`](App%20Changes%20Tracker.html): Interactive visual version log.
- [`SKILL.md`](SKILL.md): Agent system instructions and triggers.
