# Tier 1: Vibe Coding Foundations — Learning Journal

## 2026-03-23 | Learn | M01: Environment Setup

**Concepts covered:**
- CLAUDE.md Purpose and Function — it's a briefing packet for Claude, not documentation for humans. Auto-loaded every session. Already using one in JayBrain.
- CLAUDE.md Hierarchy (3 Levels) — Global (~/.claude/CLAUDE.md) > Project (repo root) > Folder (deeper). They stack, not replace. Like layers of clothing.
- The @ System — context injector. @ files, directories, or URLs in chat messages to pull content in immediately. No tool call round-trip. Like attaching a file to an email vs saying "go check the shared drive."
- @ Inside CLAUDE.md — import system. Auto-pulls referenced files on startup. Does NOT count toward file line count but DOES eat context window. Tiny suitcase full of portal guns.
- CLAUDE.md vs Regular Files — binary distinction. CLAUDE.md auto-loads. Everything else is inert until Read, @'d, or referenced by CLAUDE.md. No weight system, no spectrum.

**Key insight that clicked:**
- JJ spotted that claude-course had no CLAUDE.md — the INSTRUCTOR_GUIDE.md was doing the job of a CLAUDE.md but Claude never saw it automatically. Led to building the CLAUDE.md for this repo.

**Analogies used:**
- CLAUDE.md = briefing packet handed to a new hire (not a filing cabinet handbook)
- @ = attaching a file to an email vs "go check the shared drive"
- 3-level hierarchy = layers of clothing (base layer, jacket, hat)
- @ imports in CLAUDE.md = tiny suitcase full of portal guns to other dimensions
- Context budget = three methods (CLAUDE.md always-on, @ on-demand, Read tool selective)

**Misconceptions caught:** None

**Exercises completed:**
- Built CLAUDE.md for claude-course repo (collaborative design, 7 blocks, 52 lines)
- Created progress tracking system (STATE.md + 5 tier logs)
