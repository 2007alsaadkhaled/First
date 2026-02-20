# First

Claude Code + n8n MCP Setup

## Overview

This project connects Claude Code to your n8n instance via MCP (Model Context Protocol), allowing Claude to create, read, and manage n8n workflows directly.

## n8n Instance

- **URL:** http://n8n.srv1236312.hstgr.cloud
- **API:** http://n8n.srv1236312.hstgr.cloud/api/v1

## Setup

### 1. Install Claude Code (if not already)

```bash
npm install -g @anthropic-ai/claude-code
```

### 2. Configure MCP for n8n

Copy the example settings to your Claude Code config:

```bash
cp .claude/settings.example.json ~/.claude/settings.json
```

Then edit `~/.claude/settings.json` and replace `YOUR_N8N_API_KEY_HERE` with your actual n8n API key.

> **Note:** Never commit `~/.claude/settings.json` — it contains your API key.

### 3. Restart Claude Code

After saving the config, restart Claude Code. The n8n MCP server will start automatically via `npx`.

### 4. Verify connection

In Claude Code, you should now be able to say:

> *"List my n8n workflows"*
> *"Create a new n8n workflow that sends an email when a webhook is triggered"*
> *"Show me all active workflows in n8n"*

## How it works

Claude Code connects to n8n using the [n8n-mcp](https://www.npmjs.com/package/n8n-mcp) server, which wraps the n8n REST API and exposes it as MCP tools.

## Requirements

- Node.js 18+
- Access to the n8n instance at http://n8n.srv1236312.hstgr.cloud
- A valid n8n API key (generate in n8n → Settings → API)
