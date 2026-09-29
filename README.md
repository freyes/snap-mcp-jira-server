# mcp-jira-server snap

Snap package for [mcp-jira-server](https://github.com/edrich13/mcp-jira-server), a Model Context Protocol (MCP) server for self-hosted Jira instances with Personal Access Token (PAT) authentication.

## Install

[![Get it from the Snap Store](https://snapcraft.io/static/images/badges/en/snap-store-black.svg)](https://snapcraft.io/mcp-jira-server)

```bash
sudo snap install mcp-jira-server
```

## Configure

Set the required environment variables:

```bash
export JIRA_BASE_URL="https://jira.example.com"
export JIRA_PAT="your-personal-access-token"
```

Optional:

```bash
export JIRA_USER_AGENT="custom-user-agent"
```

## Usage

For Claude Desktop, add to your `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "jira": {
      "command": "mcp-jira-server",
      "env": {
        "JIRA_BASE_URL": "https://jira.example.com",
        "JIRA_PAT": "your-personal-access-token-here"
      }
    }
  }
}
```

## Build from source

```bash
snapcraft pack --use-lxd -v
sudo snap install --dangerous mcp-jira-server_*.snap
```