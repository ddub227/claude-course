# Claude Code Mastery — Setup Guide

**Course:** Claude Code Mastery (CCM) v1.0.0

This guide ensures your environment is ready for every module in the course.

---

## Required Software

### Core (Required for all modules)

| Software | Version | Purpose | Install |
|----------|---------|---------|---------|
| Claude Code CLI | Latest | The tool we're mastering | `npm install -g @anthropic-ai/claude-code` |
| Node.js | 18+ | Required for Claude Code | [nodejs.org](https://nodejs.org) |
| Git | 2.30+ | Version control integration | [git-scm.com](https://git-scm.com) |
| GitHub CLI (`gh`) | Latest | PR workflows | `npm install -g gh` or [cli.github.com](https://cli.github.com) |

### Authentication

| Account | Purpose | Modules |
|---------|---------|---------|
| Anthropic (Claude) | API access / subscription | All |
| GitHub | PR workflows, CI/CD | M08, M20 |

### Optional (Module-Specific)

| Software | Purpose | Modules |
|----------|---------|---------|
| Python 3.10+ | MCP server development | M24, M25 |
| Chromium + Playwright | Browser automation | M16 |
| Patchright | Stealth browser mode | M16 |
| jq | JSON processing in SDK mode | M14, M20 |
| Docker | Sandboxing exercises | M11 |
| VS Code or JetBrains IDE | IDE integration testing | M15 |

---

## Environment Setup

### Step 1: Install Claude Code

```bash
npm install -g @anthropic-ai/claude-code
claude --version
```

### Step 2: Authenticate

```bash
claude auth login
claude auth status
```

### Step 3: Verify Installation

```bash
claude /doctor
```

This runs the built-in health check. All items should pass.

### Step 4: Create Practice Project

```bash
mkdir ~/projects/ccm-sandbox
cd ~/projects/ccm-sandbox
git init
echo "# CCM Sandbox" > README.md
git add README.md
git commit -m "Initial commit"
```

This sandbox project is where you'll do hands-on exercises without affecting real projects.

### Step 5: Verify SynapseForge Integration

If using the JayBrain MCP system for quiz tracking:

```bash
# Verify the CCM subject exists
# In a Claude Code session:
# forge_subject_list() should show "Claude Code Mastery (CCM)"
```

---

## Environment Verification Checklist

Run these commands and verify all pass before starting Module 1:

```bash
# Claude Code installed and accessible
claude --version

# Authenticated
claude auth status

# Git available
git --version

# GitHub CLI available (for M08, M20)
gh --version

# Health check passes
claude /doctor

# Practice project ready
ls ~/projects/ccm-sandbox/
```

---

## Recommended Terminal Setup

For the best experience across all modules:

- **Terminal:** Windows Terminal, iTerm2, WezTerm, Ghostty, or Kitty
  - These support `Shift+Enter` for multiline input
  - Standard terminals require `\` + Enter or `Ctrl+J`
- **Shell:** bash or zsh (Claude Code defaults)
- **Font:** Any monospace font with ligature support recommended
- **Screen:** Minimum 120 columns wide for readable tool output

---

## Module-Specific Setup

### Module 11 (Sandboxing)
Sandbox features require platform-specific support. Check your OS:
- Linux: Full support
- macOS: Full support
- Windows: Requires WSL for full sandbox features

### Module 16 (Browser Automation)
```bash
pip install playwright
playwright install chromium

# For stealth mode:
pip install patchright
patchright install chromium
```

### Module 24 (Building MCP Servers)
```bash
# Python server development
pip install mcp[cli]

# Node.js server development
npm install @modelcontextprotocol/sdk
```

### Module 25 (Agent SDK)
```bash
# Python SDK
pip install anthropic

# Node.js SDK
npm install @anthropic-ai/sdk
```

---

## Troubleshooting

### Claude Code won't start
```bash
claude /doctor          # Run health check
claude --debug          # Start with debug output
```

### Authentication issues
```bash
claude auth logout
claude auth login       # Re-authenticate
```

### MCP server connection failures
```bash
claude mcp list         # Verify server config
# Check MCP_TIMEOUT env var (default: 10000ms)
export MCP_TIMEOUT=30000  # Increase if needed
```

### Permission denied errors
```bash
claude /permissions     # Review current permission rules
```
