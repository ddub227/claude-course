# Claude Code Mastery — Assessment Rubric

**Course:** Claude Code Mastery (CCM) v1.0.0
**Assessment Engine:** SynapseForge (spaced repetition + confidence-weighted scoring)

---

## Scoring Methodology

### Confidence-Weighted Scoring

Every quiz response is evaluated on two dimensions: **correctness** and **confidence** (self-reported 1-5 scale).

| Outcome | Confidence | Mastery Delta | Classification |
|---------|-----------|---------------|----------------|
| Correct | High (4-5) | **+0.20** | Strong signal — genuine understanding |
| Correct | Low (1-3) | **+0.10** | Moderate — knows it but isn't sure yet |
| Incorrect | High (4-5) | **-0.15** | Misconception — confidently wrong (priority fix) |
| Incorrect | Low (1-3) | **-0.05** | Expected gap — knows they don't know |

### Why Confidence Matters

Confidence scoring separates four types of learners:

1. **Knows it, knows they know it** (correct + confident) — True mastery
2. **Knows it, doesn't know they know it** (correct + unsure) — Needs reinforcement
3. **Doesn't know it, thinks they do** (incorrect + confident) — DANGEROUS. Misconception.
4. **Doesn't know it, knows they don't** (incorrect + unsure) — Honest gap. Easiest to fix.

Type 3 is the most critical to address. The -0.15 penalty ensures misconceptions get flagged and re-tested aggressively.

---

## Error Classification

When an incorrect answer is given, the error is auto-classified:

| Error Type | Definition | Example |
|-----------|-----------|---------|
| **Slip** | Knew the answer, made a careless mistake | Selected A instead of B by accident |
| **Lapse** | Previously knew, temporarily forgot | Couldn't recall a flag they used last week |
| **Mistake** | Applied wrong reasoning to reach answer | Confused permission precedence order |
| **Misconception** | Fundamental misunderstanding of concept | Believes `deny` rules are lowest priority |

Error patterns are tracked per concept and surfaced via `forge_errors()` analytics.

---

## Mastery Levels

| Level | Range | Criteria | What It Means |
|-------|-------|----------|---------------|
| **Spark** | 0-20% | Initial exposure | Has seen the concept, cannot yet recall reliably |
| **Ember** | 20-40% | Basic recognition | Can recognize the concept but can't explain or apply |
| **Flame** | 40-60% | Working knowledge | Can explain and use in simple scenarios |
| **Blaze** | 60-80% | Solid understanding | Can apply in complex scenarios, understands trade-offs |
| **Inferno** | 80-95% | Near mastery | Consistent performance, rare errors |
| **FORGED** | 95%+ | Complete mastery | Can teach it, design with it, debug it under pressure |

---

## Domain Weights

Each domain contributes to the overall mastery score proportionally:

| Domain | Weight | Modules | Focus |
|--------|--------|---------|-------|
| 1.0 Foundations | 25% | M01-M05 | CLI, settings, memory, permissions |
| 2.0 Intermediate | 25% | M06-M11 | Models, context, git, MCP, hooks, sandbox |
| 3.0 Advanced | 25% | M12-M18 | Subagents, skills, SDK, remote, browser, teams |
| 4.0 Expert | 15% | M19-M23 | Enterprise, CI/CD, cost, debugging, architecture |
| 5.0 Mastery | 10% | M24-M27 | Building MCP servers, Agent SDK, vim, capstone |

---

## Bloom's Taxonomy Assessment

Questions target specific cognitive levels. Higher-tier modules demand higher cognitive levels.

| Level | Question Style | Example |
|-------|---------------|---------|
| **Remember** | "What flag does X?" "Which command does Y?" | "What flag starts Claude in print mode?" |
| **Understand** | "Why does X work this way?" "Explain the difference..." | "Why does deny take precedence over allow?" |
| **Apply** | "Given this scenario, which approach..." | "You need to auto-approve npm commands. Write the permission rule." |
| **Analyze** | "Design a system that..." "Evaluate the trade-offs..." | "Design a hook chain that enforces code review before every commit." |

---

## Passing Criteria

### Overall Pass: 95% Mastery (FORGED)

The course is considered complete when:

1. **Overall mastery >= 95%** across all weighted domains
2. **No domain below 85%** — balanced knowledge required
3. **Capstone project (M27)** completed and documented

### Capstone Evaluation Criteria

The capstone project is evaluated on:

| Criterion | Weight | Description |
|-----------|--------|-------------|
| Coverage | 30% | Uses agents, skills, hooks, MCP, permissions, memory |
| Correctness | 25% | Configuration is valid and functional |
| Architecture | 25% | Demonstrates understanding of when/why to use each feature |
| Documentation | 20% | Clear, complete, teachable to someone else |

---

## Spaced Repetition Schedule

SynapseForge uses a modified SM-2 algorithm for review scheduling:

- **New concepts:** Quizzed within the same session they're introduced
- **Correct answers:** Next review interval increases (1 day -> 3 days -> 7 days -> 14 days -> 30 days)
- **Incorrect answers:** Interval resets, concept re-enters the active review queue
- **Lapsed concepts:** Flagged as "struggling" and prioritized in study sessions

The interleaved study queue prioritizes: `high exam weight * inverse mastery` — ensuring the most important, least-mastered concepts appear first.

---

## Progress Reporting

### Per-Question Stats (After Every Answer)
- Current mastery for the tested concept
- Session accuracy (today)
- All-time accuracy

### Full Dashboard (Every 10 Questions)
- Domain mastery breakdown
- Concepts reviewed vs total
- Weak areas identified
- Study streak
- Pass probability estimate

### On-Demand Analytics
- `forge_readiness(subject_id)` — Full exam readiness report
- `forge_calibration(subject_id)` — Confidence vs performance analysis
- `forge_knowledge_map(subject_id)` — Complete domain/objective/concept map
- `forge_errors(subject_id)` — Error pattern analysis
