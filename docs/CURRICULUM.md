# Claude Code Mastery — Full Curriculum

**Course:** Claude Code Mastery (CCM) v1.0.0
**Modules:** 27 | **Tiers:** 5 | **Pass Score:** 95% (FORGED)

---

## TIER 1: FOUNDATIONS (Modules 1-5)

*Domain Weight: 25%*

### Module 1: The CLI — Every Flag, Every Argument (6%)

**Objective:** Master all Claude Code CLI invocation patterns, flags, and subcommands.

**Topics:**
- Starting sessions: `claude`, `claude "query"`, `claude -p`, `claude -c`, `claude -r`
- 50+ CLI flags: model selection, output formats, system prompt overrides, session control, MCP config, permission modes, worktrees, budget limits, debug mode
- Print mode (`-p`) vs interactive mode — when and why
- Subcommands: `claude update`, `claude auth`, `claude mcp`, `claude agents`

**Exercise:** Run 10 different flag combinations, predict the behavior before hitting enter.

### Module 2: Interactive Mode — Slash Commands & Keyboard Shortcuts (5%)

**Objective:** Navigate Claude Code sessions efficiently using every available command and shortcut.

**Topics:**
- 25+ slash commands: `/clear`, `/compact`, `/resume`, `/rewind`, `/export`, `/rename`, `/context`, `/cost`, `/status`, `/model`, `/config`, `/permissions`, `/plan`, `/agents`, `/tasks`, `/copy`, `/desktop`, `/teleport`, `/vim`, `/memory`, `/mcp`, `/hooks`, `/add-dir`, `/init`, `/doctor`, `/debug`
- All keyboard shortcuts: `Ctrl+C/D/F/L/O/R/T/V/B/G`, `Shift+Tab`, `Alt+P/T/M`, `Esc+Esc`, arrow keys
- Multiline input methods (Shift+Enter, Option+Enter, backslash+Enter, Ctrl+J)
- `!` bash mode, `@` file mentions, `/` autocomplete

**Exercise:** Navigate a full session using ONLY keyboard shortcuts.

### Module 3: The Settings Universe (5%)

**Objective:** Understand and configure Claude Code at all 4 scope levels.

**Topics:**
- 4 scopes: Managed > User > Project > Local (precedence order)
- File locations: `~/.claude/settings.json`, `.claude/settings.json`, `.claude/settings.local.json`
- Every settings field: model, permissions, hooks, env, sandbox, attribution, statusLine, availableModels, effortLevel, fileSuggestion, plugins
- 40+ environment variables that control behavior

**Exercise:** Create a settings.json from scratch that configures model, permissions, and env vars.

### Module 4: Memory — CLAUDE.md, Auto-Memory & Rules (5%)

**Objective:** Design and implement a multi-tier memory system for Claude Code projects.

**Topics:**
- Memory hierarchy: Managed > Project > User > Local > Auto-memory
- `CLAUDE.md` (team-shared) vs `CLAUDE.local.md` (personal) vs `~/.claude/CLAUDE.md` (global)
- Auto-memory: `MEMORY.md` (200 line limit), topic files, enable/disable
- Imports: `@README`, `@docs/guide.md` — max depth 5
- Modular rules: `.claude/rules/*.md` with glob-based path matching

**Exercise:** Set up a 3-tier memory system — global preferences, project conventions, local overrides.

### Module 5: Permissions — The Security Model (4%)

**Objective:** Configure fine-grained permission rules for safe, efficient Claude Code usage.

**Topics:**
- 5 permission modes: default, acceptEdits, plan, dontAsk, bypassPermissions
- Permission rules syntax: tool name, specifiers, wildcards, gitignore patterns
- `allow`, `ask`, `deny` — evaluation order (deny wins)
- Tool-specific patterns: `Bash(npm run *)`, `Read(./.env)`, `WebFetch(domain:github.com)`
- Switching modes: `Shift+Tab`, `--permission-mode`, settings.json

**Exercise:** Write a permission set that allows reads, allows specific bash commands, denies network access.

---

## TIER 2: INTERMEDIATE (Modules 6-11)

*Domain Weight: 25%*

### Module 6: Model Selection & Thinking (4%)

**Objective:** Choose the right model for each task and leverage extended thinking effectively.

**Topics:**
- Model aliases: `sonnet`, `opus`, `haiku`, `opusplan`, `default`
- Effort levels (Opus only): low, medium, high
- Extended thinking: toggle with `Alt+T`, `MAX_THINKING_TOKENS`, "ultrathink" keyword
- 1M context mode (beta), fallback models, model restrictions

**Exercise:** Solve the same problem with all 3 models, compare cost/quality/speed.

### Module 7: Context Management — The Hidden Art (5%)

**Objective:** Optimize context window usage to maximize session effectiveness.

**Topics:**
- `/context` visualization and breakdown
- What consumes context: CLAUDE.md, MCP tools, file reads, git diffs, conversation
- `/compact [instructions]` — manual compaction with focus
- Auto-compact at ~95%, configurable threshold
- Strategies: subagent isolation, skill modularization, rules files

**Exercise:** Monitor context usage across a real task, compact strategically, measure the difference.

### Module 8: Git Integration & Worktrees (3%)

**Objective:** Use Claude Code's git features for efficient version control workflows.

**Topics:**
- Branch awareness, diff viewing, commit creation
- Worktrees: `claude -w feature-name`, isolated branches in `.claude/worktrees/`
- Worktree memory isolation and cleanup
- PR workflows: `--from-pr`, `gh` CLI integration

**Exercise:** Create a worktree, make changes in isolation, merge back.

### Module 9: MCP Server Integration (5%)

**Objective:** Configure and use MCP servers to extend Claude Code with external tools.

**Topics:**
- MCP protocol fundamentals
- Transport types: HTTP, stdio
- Adding servers: `claude mcp add`, scopes (local, project, user)
- `.mcp.json` configuration, env var expansion
- Tool Search, OAuth, managed MCP policies

**Exercise:** Add a stdio MCP server, configure in .mcp.json, use its tools.

### Module 10: Hooks — Event-Driven Automation (5%)

**Objective:** Build hooks that automate workflows triggered by Claude Code events.

**Topics:**
- 15 hook events: SessionStart, UserPromptSubmit, PreToolUse, PermissionRequest, PostToolUse, PostToolUseFailure, Notification, SubagentStart, SubagentStop, Stop, TeammateIdle, TaskCompleted, ConfigChange, WorktreeCreate, WorktreeRemove, PreCompact
- 4 handler types: command, http, prompt, agent
- Exit codes: 0 (allow), 1 (error/continue), 2 (deny/block)
- Matcher syntax, chaining, conditional logic

**Exercise:** Build a PreToolUse hook that logs edits, and a PostToolUse hook that runs linting.

### Module 11: Sandboxing (3%)

**Objective:** Configure sandbox isolation for safe command execution.

**Topics:**
- What's sandboxed (Bash only) vs OS permissions
- Filesystem and network allowlists
- Configuration: `sandbox.enabled`, `allowedDomains`, `excludedCommands`
- `autoAllowBashIfSandboxed`

**Exercise:** Enable sandbox, test boundaries, configure allowlists.

---

## TIER 3: ADVANCED (Modules 12-18)

*Domain Weight: 25%*

### Module 12: Subagents — Delegation & Parallelism (5%)

**Objective:** Create and manage custom subagents for parallel, isolated task execution.

**Topics:**
- Built-in agents: Explore, Plan, General-purpose
- Custom agent files: `.claude/agents/<name>.md` with YAML frontmatter
- Configuration: tools, model, permissions, maxTurns, skills, MCP servers, memory scope, isolation, hooks
- Foreground vs background, context isolation, agent memory
- Restricting spawning: `Task(AgentName)` permissions

**Exercise:** Create 3 custom agents — code reviewer, test runner, documentation writer.

### Module 13: Skills — Reusable Workflows (5%)

**Objective:** Package reusable prompts and workflows as shareable skills.

**Topics:**
- SKILL.md format with YAML frontmatter
- Location hierarchy: `.claude/commands/` < `.claude/skills/` < `~/.claude/skills/`
- String substitutions: `$ARGUMENTS`, `$0`, `$1`, `${CLAUDE_SESSION_ID}`, shell preprocessing
- Control: `disable-model-invocation`, `user-invocable`, `allowed-tools`, `context: fork`
- Agent-backed skills

**Exercise:** Build a `/review` skill and a `/deploy` skill.

### Module 14: Headless/SDK Mode — Programmatic Claude (4%)

**Objective:** Use Claude Code programmatically in scripts and automated pipelines.

**Topics:**
- `claude -p` print mode for scripting
- Output formats: text, json, stream-json
- `--json-schema` structured output validation
- Session chaining, piping, `--allowedTools`, safety rails

**Exercise:** Build a shell script that pipes git diff into Claude for automated review.

### Module 15: Remote & Web Sessions (3%)

**Objective:** Control Claude Code remotely and move sessions between CLI and web.

**Topics:**
- Remote Control: `claude remote-control`
- Web sessions: `claude --remote`
- Teleport between CLI and web
- Desktop handoff: `/desktop`

**Exercise:** Start a remote session, teleport to CLI, continue work.

### Module 16: Browser Automation (3%)

**Objective:** Automate web interactions using Claude Code's browser tools.

**Topics:**
- Browser tool suite: launch, navigate, snapshot, click, type, hover, press_key, select_option, wait, evaluate, screenshot
- Accessibility tree and `[ref]` targeting
- Session persistence: save/load login state
- Stealth mode (Patchright)

**Exercise:** Automate a complete web workflow — login, navigate, fill form, submit.

### Module 17: Plugins & Marketplaces (2%)

**Objective:** Discover, install, and manage Claude Code plugins.

**Topics:**
- Plugin structure: skills, agents, hooks, MCP servers, LSP servers
- Installing, enabling, disabling, updating
- Official and custom marketplaces
- Enterprise controls

**Exercise:** Explore available plugins, install one, examine its structure.

### Module 18: Agent Teams — Parallel Coordination (3%)

**Objective:** Coordinate multiple agents working in parallel on complex tasks.

**Topics:**
- Teams vs subagents (parallel + independent context vs sequential)
- Teammate modes: auto, in-process, tmux
- Task assignment and synthesis
- When to use teams vs subagents vs skills

**Exercise:** Set up a team of 3 agents working on different parts of a feature.

---

## TIER 4: EXPERT (Modules 19-23)

*Domain Weight: 15%*

### Module 19: Enterprise & Managed Configuration (3%)

**Objective:** Design Claude Code configurations for team and enterprise deployments.

**Topics:**
- Managed settings paths (system-level)
- Managed MCP: `managed-mcp.json`, policy-based allowlists/denylists
- Model restrictions: `availableModels`
- Compliance hooks and audit trails

**Exercise:** Design a managed configuration for a 10-person team.

### Module 20: CI/CD Integration (4%)

**Objective:** Integrate Claude Code into continuous integration and deployment pipelines.

**Topics:**
- Headless mode in pipelines: `claude -p` with `--allowedTools`
- Budget and turn limits as safety rails
- Structured output for pipeline parsing
- GitHub Actions / GitLab CI patterns

**Exercise:** Write a GitHub Actions workflow that uses Claude for PR review.

### Module 21: Cost Optimization & Performance Tuning (3%)

**Objective:** Minimize costs while maximizing Claude Code effectiveness.

**Topics:**
- Token economics: input, output, thinking
- Model selection strategy
- Context optimization: minimize tools, compact aggressively, use subagents
- Caching and pricing tiers

**Exercise:** Audit usage, identify optimization opportunities, implement changes.

### Module 22: Debugging & Troubleshooting (3%)

**Objective:** Diagnose and resolve Claude Code issues systematically.

**Topics:**
- `/doctor` health check, `/debug` troubleshooting
- `--debug <categories>` category-filtered debug mode
- MCP server and hook debugging
- Common failure modes and fixes

**Exercise:** Intentionally break 5 things, diagnose and fix each using only debug tools.

### Module 23: Advanced Patterns & Architectures (2%)

**Objective:** Design complex multi-component Claude Code systems.

**Topics:**
- Multi-agent orchestration patterns
- Skill composition (skills invoking skills)
- Hook chains for compliance workflows
- MCP server chaining, session continuity patterns

**Exercise:** Design a complete agent architecture for a complex project.

---

## TIER 5: MASTERY (Modules 24-27)

*Domain Weight: 10%*

### Module 24: Building Custom MCP Servers (4%)

**Objective:** Build and publish custom MCP servers to extend Claude Code.

**Topics:**
- MCP protocol deep dive: tools, resources, prompts
- Building stdio servers (Python FastMCP, Node SDK)
- Building HTTP servers
- Tool definitions, input schemas, return types
- Testing, debugging, publishing

**Exercise:** Build a custom MCP server that wraps your favorite API.

### Module 25: The Claude Agent SDK (3%)

**Objective:** Build standalone agent applications using the Claude SDK.

**Topics:**
- Programmatic agent creation beyond CLI
- Custom agent loops with tool use
- Multi-agent coordination in code
- Streaming, structured output, error handling
- Application integration

**Exercise:** Build a standalone agent application using the SDK.

### Module 26: Vim Mode Deep Dive (1%)

**Objective:** Master vim-style editing in Claude Code.

**Topics:**
- All vim keybindings: navigation, editing, text objects, operators
- INSERT and NORMAL mode transitions
- Operators, motions, character search
- Custom keybindings in `~/.claude/keybindings.json`

**Exercise:** Edit a complete prompt using only vim mode.

### Module 27: Capstone Project (2%)

**Objective:** Demonstrate comprehensive Claude Code mastery through a complete build.

**Requirements:**
- Design and build a complete Claude Code environment from scratch
- Must include: custom agents, skills, hooks, MCP server config, permissions, memory system
- Document as a reusable template
- Present and explain all architectural decisions

**Evaluation:** Coverage (30%), Correctness (25%), Architecture (25%), Documentation (20%)

---

## APPENDICES

### Appendix A: Complete Environment Variables Reference
*(To be populated during Module 3)*

### Appendix B: Complete CLI Flags Reference
*(To be populated during Module 1)*

### Appendix C: Complete Slash Commands Reference
*(To be populated during Module 2)*

### Appendix D: Complete Keyboard Shortcuts Reference
*(To be populated during Module 2)*

### Appendix E: Settings.json Schema Reference
*(To be populated during Module 3)*

### Appendix F: Hook Events & Handler Types Reference
*(To be populated during Module 10)*

### Appendix G: Permission Rule Syntax Quick Reference
*(To be populated during Module 5)*

### Appendix H: Troubleshooting Playbook
*(To be populated during Module 22)*
