# Claude Code Setup

> A comprehensive configuration setup for Claude Code with Model Context Protocol (MCP) servers, custom commands, and automated workflows.

[![Claude Code](https://img.shields.io/badge/Claude%20Code-Compatible-blue.svg)](https://claude.ai/code)
[![MCP](https://img.shields.io/badge/MCP-Enabled-green.svg)](https://modelcontextprotocol.io/)
[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://python.org)

## Table of Contents

- [Overview](#overview)
- [Quick Start](#quick-start)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Features](#features)
- [Commands](#commands)
- [Configuration](#configuration)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

## Overview

This project provides a pre-configured environment for Claude Code with enhanced capabilities through:

- **MCP Servers**: Context7, Puppeteer, Sequential Thinking, DeepWiki
- **Custom Commands**: Intelligent workflows for commits, tasks, and problem-solving
- **Hook System**: Automated directory management and workflow triggers
- **Structured Workflows**: Organized task management with reporting and planning

## Quick Start

```bash
# 1. Install dependencies
pip install uv

# 2. Clone this configuration
git clone <your-repo> claude-setup
cd claude-setup

# 3. Start using commands
/task_medium implement user authentication
```

## Prerequisites

Before using this setup, ensure you have:

- **Claude Code**: Installed and configured
- **Python 3.8+**: For hook script execution
- **uv**: Package manager for Python script execution
- **Node.js**: For MCP server functionality (npx)

### Installation

#### 1. Install uv (if not already installed)

```bash
# macOS/Linux
curl -LsSf https://astral.sh/uv/install.sh | sh

# Windows
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"

# After installation, open a new terminal and verify:
uv --version
```

#### 2. Setup Configuration

```bash
# Copy configuration files to your project
cp -r .claude/ /your/project/
cp .mcp.json /your/project/

# Ensure hook permissions
chmod +x .claude/hooks/task_medium_prep_hook.py
```

## Features

### 🎯 Custom Commands
- **`/commit`**: Intelligent commit workflow with conventional standards
- **`/task_medium`**: Advanced problem-solving with automated directory management
- **`/task_easy`**: Simplified task workflow for lighter needs

### 🔌 MCP Servers
- **Context7**: Library documentation and code context
- **Puppeteer**: Browser automation and web scraping  
- **Sequential Thinking**: Advanced reasoning and problem-solving
- **DeepWiki**: Repository documentation fetching

### ⚡ Hook System
- **UserPromptSubmit**: Automatic directory creation for task workflows
- **Extensible**: Easy to add custom hooks for workflow automation
- **Documentation**: [Hooks Reference](https://docs.anthropic.com/en/docs/claude-code/hooks) | [Hooks Guide](https://docs.anthropic.com/en/docs/claude-code/hooks-guide)

## Commands

### `/task_medium` - Advanced Problem Solving

Automated workflow for complex problem-solving with structured investigation and planning.

**Usage:**
```bash
/task_medium [problem description]
```

**Features:**
- ✅ Automatic `claude-instance-{id}` directory creation
- ✅ Sequential thinking for complex reasoning
- ✅ Codebase investigation with REPORT.md generation
- ✅ Structured planning with PLAN.md output
- ✅ Incremental instance numbering
- ✅ Edge case handling and best practices focus

**Example:**
```bash
/task_medium implement user authentication system
```

**Workflow:**
1. 🔧 Hook detects `/task_medium` prompt
2. 📁 Creates `claude-code-storage/claude-instance-{id}/` directory
3. 🔍 Subagent investigates codebase and creates REPORT.md
4. 📋 User reviews and approves plan
5. 📝 PLAN.md generated in instance directory

### `/commit` - Intelligent Commits

Analyzes code changes and follows conventional commit standards.

**Features:**
- Diff analysis and change summarization
- Conventional commit message formatting
- Temporary fix detection and warnings

### `/task_easy` - Simplified Tasks

Lightweight task workflow for simpler problem-solving needs.

## Configuration

### Directory Structure

```
claude-setup/
├── .claude/
│   ├── settings.json          # Permissions and hook configuration
│   ├── hooks/
│   │   └── task_medium_prep_hook.py  # Auto directory creation
│   └── commands/
│       ├── task_medium.md     # Advanced task workflow
│       ├── task_easy.md       # Simple task workflow
│       └── commit.md          # Commit workflow
├── .mcp.json                  # MCP server configuration
├── claude-code-storage/       # Auto-generated task directories
└── README.md
```

### Settings Configuration

The `.claude/settings.json` file contains:

```json
{
  "permissions": {
    "allow": ["WebFetch(domain:docs.anthropic.com)", ...],
    "deny": [...]
  },
  "hooks": {
    "UserPromptSubmit": [
      {
        "hooks": [
          {
            "type": "command",
            "command": "uv run .claude/hooks/task_medium_prep_hook.py"
          }
        ]
      }
    ]
  },
  "enabledMcpjsonServers": ["context7", "puppeteer", "sequential-thinking", ...]
}
```

### MCP Configuration

The `.mcp.json` file defines server configurations:

```json
{
  "mcpServers": {
    "context7": {
      "command": "npx",
      "args": ["@context7/claude-dev", "--minTokens", "1000"]
    },
    "puppeteer": {
      "command": "npx",
      "args": ["@puppeteer/claude-dev"]
    }
  }
}
```

## Troubleshooting

### Common Issues

**Hook not triggering:**
- Ensure `uv` is installed and in PATH
- Check script permissions: `chmod +x .claude/hooks/task_medium_prep_hook.py`
- Verify hook configuration in `.claude/settings.json`

**Directory creation fails:**
- Check file system permissions
- Ensure `claude-code-storage/` parent directory exists
- Review hook script logs for error details

**MCP servers not loading:**
- Verify Node.js and npx are installed
- Check `.mcp.json` configuration syntax
- Ensure MCP packages are available via npx

### Debug Mode

Enable debug mode for detailed logging:

```bash
claude --debug
```

## Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes and test thoroughly
4. Submit a pull request with detailed description

### Adding Custom Hooks

1. Create script in `.claude/hooks/`
2. Make executable: `chmod +x .claude/hooks/your_hook.py`
3. Add configuration to `.claude/settings.json`
4. Test with sample inputs

**Resources:**
- [Hooks Reference Documentation](https://docs.anthropic.com/en/docs/claude-code/hooks)
- [Hooks Implementation Guide](https://docs.anthropic.com/en/docs/claude-code/hooks-guide)

## License

This configuration setup is provided as-is for Claude Code enhancement.

---

**Need help?** Check the documentation:
- [Claude Code Main Docs](https://docs.anthropic.com/claude-code)
- [Hooks Reference](https://docs.anthropic.com/en/docs/claude-code/hooks)
- [Hooks Implementation Guide](https://docs.anthropic.com/en/docs/claude-code/hooks-guide)

Or open an issue for project-specific questions.