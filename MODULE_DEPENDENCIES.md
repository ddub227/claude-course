# Claude Code Mastery — Module Dependencies

**Course:** Claude Code Mastery (CCM) v1.0.0

This document maps prerequisite relationships between all 27 modules. A module cannot be started until all its prerequisites are complete.

---

## Dependency Graph (Text)

```
M01 (CLI Flags)
 ├── M02 (Slash Commands) ──── M26 (Vim Mode)
 ├── M08 (Git & Worktrees)
 ├── M14 (Headless/SDK) ──── M20 (CI/CD)
 ├── M15 (Remote Sessions)
 ├── M16 (Browser Automation)
 └── M03 (Settings)
      ├── M04 (Memory) ──── M07 (Context Mgmt)
      ├── M05 (Permissions)
      │    ├── M10 (Hooks) ──────────┐
      │    ├── M11 (Sandboxing)      │
      │    ├── M12 (Subagents) ──────┤
      │    │    ├── M13 (Skills)     │
      │    │    ├── M18 (Teams)      │
      │    │    └── M25 (Agent SDK)  │
      │    └── M19 (Enterprise)      │
      ├── M06 (Models) ─── M07       │
      │                    └── M21 (Cost Opt)
      └── M09 (MCP)                  │
           ├── M17 (Plugins)         │
           ├── M19 (Enterprise)      │
           ├── M22 (Debugging) ◄─────┘
           └── M24 (Building MCP)

M23 (Advanced Patterns) ◄── M10, M12, M13
M27 (Capstone) ◄── M01-M14 (all core modules)
```

---

## Prerequisites Table

| Module | Title | Prerequisites | Unlocks |
|--------|-------|---------------|---------|
| **M01** | CLI Flags & Arguments | *None* | M02, M03, M08, M14, M15, M16 |
| **M02** | Slash Commands & Shortcuts | M01 | M26 |
| **M03** | Settings Universe | M01 | M04, M05, M06, M09 |
| **M04** | Memory System | M03 | M07 |
| **M05** | Permissions | M03 | M10, M11, M12, M19 |
| **M06** | Model Selection & Thinking | M03 | M07, M21 |
| **M07** | Context Management | M04, M06 | M21 |
| **M08** | Git & Worktrees | M01 | *(none)* |
| **M09** | MCP Integration | M03 | M17, M19, M22, M24 |
| **M10** | Hooks | M03, M05 | M22, M23 |
| **M11** | Sandboxing | M05 | *(none)* |
| **M12** | Subagents | M05, M09 | M13, M18, M23, M25 |
| **M13** | Skills | M05, M12 | M23 |
| **M14** | Headless/SDK Mode | M01, M05 | M20, M25 |
| **M15** | Remote & Web Sessions | M01 | *(none)* |
| **M16** | Browser Automation | M01 | *(none)* |
| **M17** | Plugins & Marketplaces | M09 | *(none)* |
| **M18** | Agent Teams | M12 | *(none)* |
| **M19** | Enterprise Config | M03, M05, M09 | *(none)* |
| **M20** | CI/CD Integration | M14 | *(none)* |
| **M21** | Cost Optimization | M06, M07, M12 | *(none)* |
| **M22** | Debugging & Troubleshooting | M03, M09, M10 | *(none)* |
| **M23** | Advanced Patterns | M10, M12, M13 | *(none)* |
| **M24** | Building MCP Servers | M09 | *(none)* |
| **M25** | Agent SDK | M12, M14 | *(none)* |
| **M26** | Vim Mode | M02 | *(none)* |
| **M27** | Capstone Project | M01-M14 | *(none)* |

---

## Critical Path

The longest prerequisite chain (determines minimum course duration):

```
M01 → M03 → M05 → M12 → M13 → M23
  (6 modules deep, ~14.5 hours minimum)
```

The capstone (M27) requires M01-M14 (14 modules), which is the broadest prerequisite set.

---

## Recommended Learning Order

While prerequisites allow some flexibility, this is the recommended sequence:

**Phase 1 (Weeks 1-2):** M01 → M02 → M03 → M04 → M05
**Phase 2 (Weeks 3-4):** M06 → M07 → M08 → M09 → M10 → M11
**Phase 3 (Weeks 5-6):** M12 → M13 → M14 → M15 → M16 → M17 → M18
**Phase 4 (Weeks 7-8):** M19 → M20 → M21 → M22 → M23
**Phase 5 (Weeks 9-10):** M24 → M25 → M26 → M27

---

## Parallel Learning Opportunities

Some modules can be studied simultaneously if prerequisites are met:

| After completing... | You can study in parallel... |
|--------------------|-----------------------------|
| M01 | M02 + M08 + M15 + M16 |
| M03 | M04 + M05 + M06 + M09 |
| M05 | M10 + M11 |
| M05, M09 | M12 + M19 |
| M12 | M13 + M18 |
| M14 | M20 + M25 (if M12 done) |
