# Claude Code Setup

A comprehensive configuration setup for Claude Code with Model Context Protocol (MCP) servers and custom commands.

## Overview

This project provides a pre-configured environment for Claude Code with enhanced capabilities through MCP servers and custom command workflows.

## Features

### MCP Servers
- **Context7**: Library documentation and code context
- **Puppeteer**: Browser automation and web scraping
- **Sequential Thinking**: Advanced reasoning and problem-solving
- **DeepWiki**: Repository documentation fetching

### Custom Commands
- **commit**: Intelligent commit workflow with diff analysis and conventional commit standards
- **task**: Advanced problem-solving with sequential thinking and codebase investigation

## Configuration Files

### `.claude/settings.json`
Contains permissions and MCP server configurations with granular access control for various tools and domains.

### `.mcp.json`
Defines MCP server configurations including:
- Context7 with minimum token settings
- Puppeteer for browser automation
- Sequential thinking for complex reasoning
- DeepWiki for documentation access

## Getting Started

1. Ensure Claude Code is installed and configured
2. Clone or copy this configuration to your project
3. The MCP servers will be automatically available through npx

## Custom Command Usage

### Commit Command
Analyzes code changes and follows conventional commit standards while checking for temporary fixes.

### Task Command
Utilizes sequential thinking for complex problem-solving with optional codebase investigation using the `I_T` keyword.

## MCP Server Details

- **Context7**: Provides library documentation with configurable token limits
- **Puppeteer**: Enables browser automation for testing and scraping
- **Sequential Thinking**: Advanced reasoning capabilities
- **DeepWiki**: Fetches repository documentation

## License

This configuration setup is provided as-is for Claude Code enhancement.