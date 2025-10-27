# README

## Overview

Haima CAA MCP is a cloud PC and cloud phone service provided by Haima Cloud. Through the MCP service, users can remotely control cloud PCs and cloud phones, offering flexible computing resources and convenient remote access capabilities.

## Procedure

### Step 1: Create an API Key

1. Log in to [Haima CAA](https://caa.haimacloud.com/).
2. Click **API Key Management** in the left navigation panel.
3. On the service management page, click to create a new API Key.
4. In the "Create API Key" dialog box, select either Cloud PC or Cloud Phone, then click **OK**.

### Step 2: Obtain the MCP Address

On the **API Key Management** page, locate your target API Key and click **View MCP Address** in the Actions column.

### Step 3: Complete MCP Service Configuration

Add the MCP address in any tool that supports MCP, and complete the MCP service configuration.

#### Claude Desktop Integration

add to your `claude_desktop_config.json`：

```json
{
  "mcpServers": {
    "cloud_computer": {
      "url": "https://mcp-server.haimacloud.com/mcp",
      "headers": {
        "Authorization": "Bearer <you cloud computer API Key>"
      }
    },
    "cloud_phone": {
      "url": "https://mcp-server.haimacloud.com/mcp",
      "headers": {
        "Authorization": "Bearer Bearer <your cloud phone API Key>"
      }
    }
  }
}
```

#### Cursor Integration

add to your `~/.cursor/mcp.json`：

```json
{
  "mcpServers": {
    "cloud_computer": {
      "url": "https://mcp-server.haimacloud.com/mcp",
      "headers": {
        "Authorization": "Bearer <you cloud computer API Key>"
      }
    },
    "cloud_phone": {
      "url": "https://mcp-server.haimacloud.com/mcp",
      "headers": {
        "Authorization": "Bearer Bearer <your cloud phone API Key>"
      }
    }
  }
}
```
