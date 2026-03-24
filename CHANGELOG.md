# Changelog

All notable changes to the Claude Code Mastery curriculum will be documented in this file.

Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

---

## [2.0.0] - 2026-02-28

### Changed
- **MAJOR: Restructured entire curriculum around vibe coding mastery**
- Tier 1 now teaches vibe coding foundations (environment, prompting, context, memory, permissions) instead of CLI flag memorization
- Tier 2 focuses on scaling vibe coding (agents, skills, git, MCP, hooks)
- Tier 3 covers power moves (multi-agent, models, headless, browser, debug)
- Tier 4 is "The Deep Cuts" — comprehensive CLI flags, slash commands, settings deep-dive (original M01-M03 content)
- Tier 5 unchanged (Mastery: build MCP servers, SDK, plugins, capstone)
- Domain weights rebalanced: 30/25/20/15/10 (was 25/25/25/15/10)
- Updated instructor guide per-module teaching notes with vibe coding focus
- Updated README with vibe coder positioning
- All teaching notes now include "vibe coder angle" perspective

### Philosophy
- "Learn to make music FIRST, then master the mixing board"
- Every feature taught through the lens of "how does this make you a better vibe coder?"
- Scenarios over syntax — lead with the problem, reveal the feature

---

## [1.0.0] - 2026-02-27

### Added
- Initial course structure: 27 modules across 5 tiers
- Course configuration file (`course_config.yaml`) with all module definitions, weights, prerequisites, and SynapseForge mappings
- Formal syllabus with learning outcomes, pacing guide, and assessment schedule
- Setup guide with required software, environment verification, and troubleshooting
- Assessment rubric with confidence-weighted scoring methodology, mastery levels, and passing criteria
- Module dependency map with prerequisite graph and recommended learning order
- Instructor guide with per-module teaching notes, quiz protocol, and session recovery
- Student handbook with quiz protocol, scoring explanation, and tips for success
- Full curriculum outline with all 27 module descriptions and exercises
- README with quickstart and repository overview
- SynapseForge subject created: Claude Code Mastery (CCM), subject ID `dd261837f042`, pass score 95%
- 27 SynapseForge objectives loaded with weighted exam scores across 5 domains
- Google Doc created in Claude_Course folder with curriculum + progress tracker
- Triple-layer logging pipeline: SynapseForge + JayBrain memories + Google Doc progress updates
