# Pitchsmith Marketplace

Official Claude Code marketplace for the Pitchsmith plugin — AI-powered slide builder.

## Quick Start

```bash
# Step 1: Add the marketplace (one-time)
/plugin marketplace add pitchsmith/pitchsmith-marketplace

# Step 2: Install the plugin
/plugin install pitchsmith@pitchsmith-marketplace

# Step 3: Start building slides
/pitchsmith
```

## Prerequisites

- **Claude Code v1.0.33+** — Plugin system support required
- **Node.js v18+** (optional) — Required only for PNG/PDF/PPTX export features

## Available Plugins

| Plugin | Version | Category | Description |
|--------|---------|----------|-------------|
| `pitchsmith` | 0.2.10 | productivity | AI-powered slide builder — plan, build, and export brand-perfect presentations |

## What You Get

After installing Pitchsmith, you'll have access to:

- **26 slash commands** across the `/pitchsmith` namespace
- **Smart router** — `/pitchsmith` detects your workspace state and routes to the right workflow
- **Zero-config setup** — Default theme, templates, and sample deck scaffold automatically on first run
- **PDF brand extraction** — Bundled MCP server extracts colors, fonts, and logos from brand guidelines

## Team Installation

Add to your project's `.claude/settings.json` to auto-prompt teammates:

```json
{
  "extraKnownMarketplaces": {
    "pitchsmith-marketplace": {
      "source": {
        "source": "github",
        "repo": "pitchsmith/pitchsmith-marketplace"
      }
    }
  },
  "enabledPlugins": {
    "pitchsmith@pitchsmith-marketplace": true
  }
}
```

### Configuration Scope

Claude Code settings can be applied at different scopes:

| Scope | File Location | Use Case |
|-------|--------------|----------|
| **Project** | `.claude/settings.json` (in repo root) | Team-wide adoption — committed to version control so all team members get prompted |
| **Local** | `.claude/settings.local.json` (in repo root) | Personal project settings — gitignored, not shared with team |
| **User** | `~/.claude/settings.json` (home directory) | Personal global settings — applies across all projects |

For team adoption, use **project** scope so the configuration is shared via version control.

## Troubleshooting

**"Plugin not found" after marketplace add:**
Ensure you're running Claude Code v1.0.33 or later. Check with `claude --version`.

**Export features not working:**
PNG, PDF, and PPTX export require Node.js v18+. Install from [nodejs.org](https://nodejs.org).

**PDF brand extraction unavailable:**
The pdf-reader MCP server requires Node.js and npx. Verify with `npx --version`. The MCP server starts automatically when the plugin loads — no manual configuration needed.

**Commands not appearing:**
Try `/plugin disable pitchsmith@pitchsmith-marketplace` then `/plugin enable pitchsmith@pitchsmith-marketplace` to refresh.

## License

ELv2
