# Claude Code Mastery — Full Curriculum

**Course:** Claude Code Mastery (CCM) v2.0.0 — Vibe Coder Edition
**Modules:** 27 | **Tiers:** 5 | **Pass Score:** 95% (FORGED)
**Focus:** Master vibe coding first. Deep technical knowledge second.

---

## Philosophy: Vibe Coding First

Traditional Claude Code training teaches you every button on the mixing board before you play a note. This curriculum flips that: **you learn to make music FIRST, then master the board.**

**What is vibe coding?** Describing what you want in natural language and letting Claude build it. You're the architect, Claude is the construction crew. Your job is communicating vision, reviewing output, and iterating — not typing code.

**What separates a good vibe coder from a GREAT one?**

1. **Environment** — Claude knows your project before you say a word
2. **Communication** — You describe what you want precisely and efficiently
3. **Context** — You manage Claude's attention like a precious resource
4. **Delegation** — You know when to let Claude drive and when to take the wheel
5. **Tooling** — You extend Claude's capabilities to match your workflow

---

## TIER 1: VIBE CODING FOUNDATIONS (Modules 1-5)

*Domain Weight: 30%*

### Module 1: Your First Vibe — Environment Setup (7%)

**Objective:** Configure Claude Code so it understands your project from the very first prompt.

**Topics:**
- CLAUDE.md — your project's brain (what it is, what goes in it, where it lives)
- The 3-file memory stack: global (`~/.claude/CLAUDE.md`), project (`.claude/CLAUDE.md`), personal (`.claude/CLAUDE.local.md`)
- Essential `settings.json` configuration for vibe coding
- Permission modes: which one lets you flow without constant interruptions?
- The 5-minute setup that transforms every vibe coding session
- Before vs after: what happens when Claude flies blind vs. when it knows your project

**Exercise:** Set up CLAUDE.md + settings for an existing project. Run the same prompt WITH and WITHOUT setup — compare results.

### Module 2: The Art of the Ask — Prompt Mastery (7%)

**Objective:** Communicate with Claude effectively to get exactly what you want, fast.

**Topics:**
- The anatomy of a great vibe coding prompt
- Describing features, bugs, and refactors in natural language
- Iterative refinement — "not quite, try this instead" patterns
- Plan mode (`/plan`) — making Claude think before it codes
- `@` file mentions — pointing Claude at specific files
- `!` bash mode — quick system commands without leaving the conversation
- When to be specific vs. when to let Claude decide
- The "too vague" vs "too specific" spectrum — finding the sweet spot

**Exercise:** Build a complete feature using ONLY natural language prompts. Zero manual code.

### Module 3: Context is King — Session Management (6%)

**Objective:** Manage Claude's context window to maintain quality across long vibe coding sessions.

**Topics:**
- What IS the context window and why it makes or breaks your vibe?
- `/context` — see what's eating your context right now
- `/compact [instructions]` — strategic compaction with focus
- Auto-compact behavior and thresholds
- Session strategies: `-c` (continue), `-r` (resume specific), fresh start
- The "session sprawl" problem — when Claude starts forgetting what you're building
- Signs Claude is losing the plot (and what to do immediately)

**Exercise:** Run a real vibe coding task, monitor context with `/context`, compact strategically, measure the quality difference.

### Module 4: Memory Architecture — Making Claude Remember (5%)

**Objective:** Design a memory system so Claude remembers your conventions, patterns, and preferences across every session.

**Topics:**
- CLAUDE.md deep dive — what sections to include, how to structure it
- Auto-memory: `MEMORY.md` (200-line limit), topic files as overflow
- Rules files: `.claude/rules/*.md` with glob-based path matching
- The `@` import system — pulling in docs, README, guides (max depth 5)
- `CLAUDE.local.md` — personal preferences that don't go in git
- Designing memory for YOUR project type (web app, API, data pipeline, etc.)

**Exercise:** Design a 3-tier memory system for a real project. Test that Claude follows your conventions without being told.

### Module 5: Frictionless Flow — Permissions & Sandboxing (5%)

**Objective:** Configure permissions so Claude can work without constant interruptions while staying safe.

**Topics:**
- 5 permission modes: default, acceptEdits, plan, dontAsk, bypassPermissions
- The vibe coder's permission setup — what to auto-allow, what to gate
- Allow/deny rules and tool specifiers: `Bash(npm run *)`, `Read(.env)`
- Sandboxing: safe execution with `autoAllowBashIfSandboxed`
- `Shift+Tab` to switch modes mid-session
- The "trust but verify" philosophy — speed without recklessness

**Exercise:** Configure a permission setup for worry-free vibe coding. Test that dangerous commands are still blocked.

---

## TIER 2: SCALING YOUR VIBE (Modules 6-10)

*Domain Weight: 25%*

### Module 6: Delegation — Agents & Subagents (6%)

**Objective:** Let Claude spawn helpers so you can tackle bigger projects without context overload.

**Topics:**
- What agents are and why they're a vibe coder's secret weapon
- Built-in agents: Explore, Plan, General-purpose
- Custom agents: `.claude/agents/<name>.md` with YAML frontmatter
- Agent configuration: tools, model, permissions, maxTurns
- Foreground vs background agents — when to watch, when to fire-and-forget
- Context isolation — why agents don't pollute your main session
- When to delegate vs. when to handle it yourself

**Exercise:** Create 3 custom agents for your workflow — code reviewer, test runner, documentation writer.

### Module 7: Skills — Your Personal Command Library (5%)

**Objective:** Package your most common workflows into reusable slash commands.

**Topics:**
- What skills are (reusable prompt + workflow packages)
- SKILL.md format with YAML frontmatter
- Location hierarchy: project `.claude/skills/` < user `~/.claude/skills/`
- String substitutions: `$ARGUMENTS`, `$0`, `$1`
- User-invocable skills vs. agent-only skills
- Agent-backed skills — skills that spawn agents
- Skills + agents = powerful workflow automation

**Exercise:** Build 2 skills that automate your most common vibe coding tasks.

### Module 8: Git Flow — Version Control on Autopilot (4%)

**Objective:** Let Claude handle git operations so you stay focused on building.

**Topics:**
- Claude's git awareness (branch, diff, status — always knows the state)
- Letting Claude commit with meaningful messages
- Worktrees: parallel features in `.claude/worktrees/`
- PR workflows: `--from-pr`, `gh` CLI integration
- The vibe coder's git workflow: describe feature → Claude builds + commits + PRs

**Exercise:** Build a feature end-to-end: prompt → code → commit → PR — all through natural language.

### Module 9: MCP Servers — Extending Claude's Reach (5%)

**Objective:** Add external tools and integrations that make Claude more capable for your workflows.

**Topics:**
- What MCP servers are (plugins/extensions for Claude)
- Transport types: stdio, HTTP
- Adding servers: `claude mcp add`, `.mcp.json` configuration
- Essential MCP servers for vibe coders
- Environment variable expansion for secrets
- Tool Search for discovering available tools
- Scopes: local, project, user

**Exercise:** Add an MCP server and use its tools in a real vibe coding session.

### Module 10: Hooks — Event-Driven Automation (5%)

**Objective:** Build automated quality checks that run silently behind every vibe coding action.

**Topics:**
- What hooks are (event → action triggers that fire automatically)
- Key events: PreToolUse, PostToolUse, Stop, SessionStart
- 4 handler types: command, http, prompt, agent
- Exit codes: 0 (allow), 1 (error/continue), 2 (deny/block)
- Auto-linting on every edit — catch mistakes before they compound
- Auto-testing on every save — instant feedback loop
- Building a "safety net" that catches errors you'd never notice

**Exercise:** Build a hook system that auto-lints and auto-tests your vibe-coded output.

---

## TIER 3: POWER MOVES (Modules 11-16)

*Domain Weight: 20%*

### Module 11: Multi-Agent Orchestration (4%)

**Objective:** Coordinate multiple agents working in parallel for complex, multi-part features.

**Topics:**
- Teams vs subagents: parallel + independent context vs sequential
- Teammate modes: auto, in-process, tmux
- Task assignment and synthesis
- When to use teams vs. subagents vs. skills

**Exercise:** Set up a team of 3 agents building different parts of a feature simultaneously.

### Module 12: Model Selection Strategy (3%)

**Objective:** Pick the right model for each task to optimize quality, speed, and cost.

**Topics:**
- Model aliases: `sonnet`, `opus`, `haiku`, `opusplan`
- When to use each: quick tasks vs. complex reasoning vs. cost-sensitive
- Extended thinking: `Alt+T`, `MAX_THINKING_TOKENS`, "ultrathink"
- Effort levels (Opus only): low, medium, high
- The hybrid approach: `opusplan` (Opus plans, Sonnet executes)
- Cost vs quality tradeoffs for vibe coding

**Exercise:** Same vibe coding task with all 3 models — compare output quality, speed, and cost.

### Module 13: Headless & SDK — Claude in Your Pipeline (4%)

**Objective:** Use Claude programmatically for automated workflows and pipelines.

**Topics:**
- `claude -p` (print mode) for scripting
- Output formats: text, json, stream-json
- `--json-schema` for guaranteed structured output
- Session chaining and piping
- `--allowedTools` and safety rails
- Building automated review/test/deploy pipelines

**Exercise:** Build a script that pipes git diff into Claude for automated code review.

### Module 14: Browser Automation (3%)

**Objective:** Automate web interactions through Claude.

**Topics:**
- Browser tool suite: launch, navigate, snapshot, click, type
- Accessibility tree and `[ref]` targeting
- Session persistence for login state
- Stealth mode (Patchright)

**Exercise:** Automate a complete web workflow — login, navigate, fill form, submit.

### Module 15: Remote & Web Sessions (3%)

**Objective:** Control Claude remotely and seamlessly move between CLI and web.

**Topics:**
- Remote Control: `claude remote-control`
- Web sessions: `claude --remote`
- Teleport between CLI and web
- Desktop handoff: `/desktop`

**Exercise:** Start a remote session, teleport to CLI, continue work seamlessly.

### Module 16: Debugging & Recovery (3%)

**Objective:** Diagnose and fix issues when vibe coding sessions go wrong.

**Topics:**
- `/doctor` health check, `/debug` troubleshooting mode
- Common vibe coding failure modes and how to fix them
- When to restart a session vs. when to fix in place
- Context window recovery strategies
- MCP server and hook debugging

**Exercise:** Intentionally break 5 things, diagnose and fix each using only debug tools.

---

## TIER 4: THE DEEP CUTS (Modules 17-22)

*Domain Weight: 15%*

### Module 17: CLI Flags — The Complete Reference (3%)

**Objective:** Know every CLI flag and when you'd actually use each one.

**Topics:**
- 50+ CLI flags organized by 9 categories
- Session control, model selection, output format flags
- System prompt overrides, permission flags
- MCP config, debug, budget limit flags
- Subcommands: `claude update`, `claude auth`, `claude mcp`, `claude agents`

**Exercise:** Run 10 different flag combinations, predict behavior before hitting enter.

### Module 18: Slash Commands & Shortcuts Mastery (3%)

**Objective:** Navigate Claude Code sessions at maximum speed with muscle memory.

**Topics:**
- 25+ slash commands and their use cases
- All keyboard shortcuts: Ctrl, Alt, Shift, Esc combinations
- Multiline input methods
- Speed drills and muscle memory training

**Exercise:** Navigate a full session using ONLY keyboard shortcuts — no mouse, no slash commands.

### Module 19: The Settings Universe — Every Knob (3%)

**Objective:** Understand and configure every setting at all 4 scope levels.

**Topics:**
- 4 scopes: Managed > User > Project > Local (precedence order)
- Every settings field (model, permissions, hooks, env, sandbox, etc.)
- 40+ environment variables that control behavior
- Advanced configuration patterns

**Exercise:** Create a complete settings.json from scratch with model, permissions, hooks, and env vars.

### Module 20: Cost Optimization & Performance (2%)

**Objective:** Minimize costs while maximizing vibe coding effectiveness.

**Topics:**
- Token economics: input, output, thinking tokens
- Context optimization strategies (minimize tools, compact, subagents)
- Caching and pricing tiers
- Budget management: `--max-budget-usd`

**Exercise:** Audit your usage, identify optimization opportunities, implement changes.

### Module 21: Enterprise & Team Patterns (2%)

**Objective:** Design Claude Code configurations for team and enterprise deployments.

**Topics:**
- Managed settings (system-level administration)
- Managed MCP: `managed-mcp.json`, policy-based controls
- Model restrictions: `availableModels`
- Compliance hooks and audit trails
- CI/CD integration patterns (GitHub Actions, GitLab CI)

**Exercise:** Design a managed configuration for a 10-person development team.

### Module 22: Advanced Architecture (2%)

**Objective:** Design complex multi-component Claude Code systems.

**Topics:**
- Multi-agent orchestration patterns
- Skill composition (skills invoking skills)
- Hook chains for compliance workflows
- MCP server chaining, session continuity patterns

**Exercise:** Design a complete agent architecture for a complex project.

---

## TIER 5: MASTERY (Modules 23-27)

*Domain Weight: 10%*

### Module 23: Building Custom MCP Servers (3%)

**Objective:** Build and publish custom MCP servers to extend Claude Code.

**Topics:**
- MCP protocol deep dive: tools, resources, prompts
- Building stdio servers (Python FastMCP, Node SDK)
- Building HTTP servers
- Tool definitions, input schemas, return types
- Testing, debugging, publishing

**Exercise:** Build a custom MCP server that wraps your favorite API.

### Module 24: The Claude Agent SDK (3%)

**Objective:** Build standalone agent applications using the Claude SDK.

**Topics:**
- Programmatic agent creation beyond CLI
- Custom agent loops with tool use
- Multi-agent coordination in code
- Streaming, structured output, error handling
- Application integration

**Exercise:** Build a standalone agent application using the SDK.

### Module 25: Plugins & Marketplaces (1.5%)

**Objective:** Discover, install, and manage Claude Code plugins.

**Topics:**
- Plugin structure: skills, agents, hooks, MCP servers, LSP servers
- Installing, enabling, disabling, updating
- Official and custom marketplaces
- Enterprise controls

**Exercise:** Explore available plugins, install one, examine its structure.

### Module 26: Vim Mode (0.5%)

**Objective:** Master vim-style editing in Claude Code's input.

**Topics:**
- All vim keybindings: navigation, editing, text objects
- INSERT and NORMAL mode transitions
- Custom keybindings in `~/.claude/keybindings.json`

**Exercise:** Edit a complete prompt using only vim mode.

### Module 27: Capstone Project (2%)

**Objective:** Demonstrate comprehensive Claude Code mastery through a complete build.

**Requirements:**
- Design and build a complete Claude Code environment from scratch
- Must include: custom agents, skills, hooks, MCP server config, permissions, memory system
- Must demonstrate effective vibe coding workflow end-to-end
- Document as a reusable template
- Present and explain all architectural decisions

**Evaluation:** Coverage (30%), Correctness (25%), Architecture (25%), Documentation (20%)

---

## APPENDICES

### Appendix A: Vibe Coding Quick Reference
*(To be populated during Module 2)*

### Appendix B: CLAUDE.md Template Library
*(To be populated during Module 1)*

### Appendix C: Complete CLI Flags Reference
*(To be populated during Module 17)*

### Appendix D: Complete Slash Commands Reference
*(To be populated during Module 18)*

### Appendix E: Complete Keyboard Shortcuts Reference
*(To be populated during Module 18)*

### Appendix F: Settings.json Schema Reference
*(To be populated during Module 19)*

### Appendix G: Hook Events & Handler Types Reference
*(To be populated during Module 10)*

### Appendix H: Permission Rule Syntax Quick Reference
*(To be populated during Module 5)*

### Appendix I: Troubleshooting Playbook
*(To be populated during Module 16)*
