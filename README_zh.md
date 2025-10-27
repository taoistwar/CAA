# README

## 概述

MCP（MCloud Platform）是海马云提供的云电脑、云手机服务，通过 MCP 服务，可以实现对云电脑、云手机的远程控制，提供灵活的计算资源和便捷的远程访问功能。

## 操作步骤

### 步骤 1：创建 API Key

1. 登录 [海马 CAA](https://caa.haimacloud.com/)
2. 在左侧导航栏中单击 "API Key 管理"。
3. 在服务管理页面上单击创建新的 API Key。
4. 在创建 API KEY 对话框中选择是云电脑、云手机，并单击确定。

### 步骤 2：获取 MCP 地址

在 "API Key 管理" 页面上，在目标 API KEY 的操作列中单击查看 MCP 地址。

### 步骤 3：完成 MCP 服务配置

在支持 MCP 的工具中添加 MCP 地址，并完成 MCP 服务配置。

#### Claude 桌面集成

添加到您的 `claude_desktop_config.json`：

```json
{
  "mcpServers": {
    "cloud_computer": {
      "url": "https://mcp-server.haimacloud.com/mcp",
      "headers": {
        "Authorization": "Bearer <您的云电脑API密钥>"
      }
    },
    "cloud_phone": {
      "url": "https://mcp-server.haimacloud.com/mcp",
      "headers": {
        "Authorization": "Bearer Bearer <您的云手机API密钥>"
      }
    }
  }
}
```

#### Cursor 集成

添加到您的 `~/.cursor/mcp.json`：

```json
{
  "mcpServers": {
    "cloud_computer": {
      "url": "https://mcp-server.haimacloud.com/mcp",
      "headers": {
        "Authorization": "Bearer <您的云电脑API密钥>"
      }
    },
    "cloud_phone": {
      "url": "https://mcp-server.haimacloud.com/mcp",
      "headers": {
        "Authorization": "Bearer Bearer <您的云手机API密钥>"
      }
    }
  }
}
```
