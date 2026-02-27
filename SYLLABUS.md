# Claude Code Mastery — Syllabus

**Course:** Claude Code Mastery (CCM)
**Version:** 1.0.0
**Pass Threshold:** 95% (Forged)
**Estimated Duration:** 40-60 hours
**Delivery:** Interactive sessions + reference documentation
**Assessment:** SynapseForge-powered spaced repetition quizzes

---

## Course Description

A comprehensive, production-grade curriculum covering every feature, configuration option, and advanced pattern in Claude Code CLI. Organized into 5 progressive tiers (27 modules), this course takes the learner from foundational CLI usage through enterprise architecture and custom tooling.

## Learning Outcomes

Upon completion, the learner will be able to:

1. **Use every CLI flag, slash command, and keyboard shortcut** with confidence
2. **Configure Claude Code** at all 4 scope levels (managed, user, project, local) including settings, memory, permissions, and environment variables
3. **Design and implement MCP servers** to extend Claude Code with custom tools
4. **Build custom subagents and skills** for reusable, team-shareable workflows
5. **Author hooks** for event-driven automation across all 15 hook events
6. **Optimize context usage, cost, and performance** through model selection, compaction, and architectural patterns
7. **Integrate Claude Code into CI/CD pipelines** using headless/SDK mode
8. **Debug and troubleshoot** sessions, MCP servers, hooks, and permissions
9. **Architect multi-agent systems** using subagents, skills, hooks, and teams
10. **Build production-grade Claude Code environments** for teams and enterprises

---

## Prerequisites

- Familiarity with a command-line terminal (bash/zsh/PowerShell)
- Git basics (clone, commit, push, branch)
- A Claude Code subscription (Pro, Max, Teams, or Enterprise)
- Claude Code CLI installed and authenticated

---

## Grading & Assessment

### Mastery Measurement

All assessment is powered by SynapseForge with confidence-weighted scoring:

| Outcome | Mastery Delta | Signal |
|---------|--------------|--------|
| Correct + Confident (confidence >= 4) | +0.20 | Strong understanding |
| Correct + Unsure (confidence < 4) | +0.10 | Moderate understanding |
| Incorrect + Confident (confidence >= 4) | -0.15 | Misconception detected |
| Incorrect + Unsure (confidence < 4) | -0.05 | Expected knowledge gap |

### Mastery Levels

| Level | Range | Meaning |
|-------|-------|---------|
| Spark | 0-20% | Just getting started |
| Ember | 20-40% | Building heat |
| Flame | 40-60% | Gaining momentum |
| Blaze | 60-80% | Seriously cooking |
| Inferno | 80-95% | Near mastery |
| FORGED | 95%+ | Complete mastery — course passed |

### Bloom's Taxonomy Progression

Each module targets specific cognitive levels:

- **Remember** — Recall facts, flags, commands
- **Understand** — Explain concepts, describe behavior
- **Apply** — Use features to solve problems
- **Analyze** — Design architectures, evaluate trade-offs

Higher-tier modules emphasize Analyze; lower tiers build from Remember upward.

---

## Pacing Guide

### Tier 1: Foundations (Modules 1-5) — ~9 hours
Recommended: 3-4 sessions over 1-2 weeks

| Module | Title | Hours | Bloom's |
|--------|-------|-------|---------|
| M01 | The CLI — Every Flag, Every Argument | 2.0 | R, U, Ap |
| M02 | Interactive Mode — Slash Commands & Shortcuts | 1.5 | R, U, Ap |
| M03 | The Settings Universe | 2.0 | R, U, Ap |
| M04 | Memory — CLAUDE.md, Auto-Memory & Rules | 2.0 | R, U, Ap, An |
| M05 | Permissions — The Security Model | 1.5 | R, U, Ap, An |

### Tier 2: Intermediate (Modules 6-11) — ~11 hours
Recommended: 4-5 sessions over 2 weeks

| Module | Title | Hours | Bloom's |
|--------|-------|-------|---------|
| M06 | Model Selection & Thinking | 1.5 | R, U, Ap |
| M07 | Context Management — The Hidden Art | 2.0 | U, Ap, An |
| M08 | Git Integration & Worktrees | 1.5 | R, U, Ap |
| M09 | MCP Server Integration | 2.5 | R, U, Ap, An |
| M10 | Hooks — Event-Driven Automation | 2.5 | U, Ap, An |
| M11 | Sandboxing | 1.0 | R, U, Ap |

### Tier 3: Advanced (Modules 12-18) — ~11.5 hours
Recommended: 4-5 sessions over 2 weeks

| Module | Title | Hours | Bloom's |
|--------|-------|-------|---------|
| M12 | Subagents — Delegation & Parallelism | 2.5 | U, Ap, An |
| M13 | Skills — Reusable Workflows | 2.0 | U, Ap, An |
| M14 | Headless/SDK Mode — Programmatic Claude | 2.0 | U, Ap, An |
| M15 | Remote & Web Sessions | 1.0 | R, U, Ap |
| M16 | Browser Automation | 1.5 | R, U, Ap |
| M17 | Plugins & Marketplaces | 1.0 | R, U |
| M18 | Agent Teams — Parallel Coordination | 1.5 | U, Ap, An |

### Tier 4: Expert (Modules 19-23) — ~8.5 hours
Recommended: 3-4 sessions over 1-2 weeks

| Module | Title | Hours | Bloom's |
|--------|-------|-------|---------|
| M19 | Enterprise & Managed Configuration | 1.5 | U, Ap, An |
| M20 | CI/CD Integration | 2.0 | U, Ap, An |
| M21 | Cost Optimization & Performance Tuning | 1.5 | U, Ap, An |
| M22 | Debugging & Troubleshooting | 1.5 | U, Ap, An |
| M23 | Advanced Patterns & Architectures | 2.0 | An |

### Tier 5: Mastery (Modules 24-27) — ~11 hours
Recommended: 4-5 sessions over 2 weeks

| Module | Title | Hours | Bloom's |
|--------|-------|-------|---------|
| M24 | Building Custom MCP Servers | 3.0 | U, Ap, An |
| M25 | The Claude Agent SDK | 3.0 | U, Ap, An |
| M26 | Vim Mode Deep Dive | 1.0 | R, Ap |
| M27 | Capstone Project | 4.0 | An |

---

## Assessment Schedule

- **Per-module quizzes:** Concepts added to SynapseForge as each module is taught. Quizzed via spaced repetition across all subsequent sessions.
- **Milestone checkpoints:** Every 10 cumulative quiz questions, a full dashboard is displayed showing domain breakdown, accuracy, and mastery progression.
- **Readiness check:** `forge_readiness(subject_id)` available at any time to see pass probability and per-domain breakdown.
- **Capstone (M27):** Build a complete Claude Code environment from scratch. Evaluated on coverage, correctness, and documentation quality.
