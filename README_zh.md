# **CAA (Control Any App) by 海马云**

## **1. 项目简介**

CAA (Control Any App) 是由业界领先的云电脑与云手机服务提供商——**海马云**——推出的创新性MCP（模型上下文协议）服务。

我们致力于打破AI大模型与云端应用生态之间的壁壁垒。通过CAA，开发者和企业用户可以获得一个强大的API Key，将任何大语言模型（LLM）与海马云平台上的云电脑及云手机实例无缝连接。这意味着，您不再需要复杂的脚本或手动干预，只需通过自然语言或简单的代码指令，就能让AI驱动成百上千台云设备，像真人一样执行应用启动、内容渲染、信息查询、批量操作等一系列复杂任务，将自动化与智能化提升至全新高度。

## **2. 核心功能**

*   **应用级精细控制**：能够精确启动、关闭或操作云设备内的指定应用程序（APP），实现从宏观调度到微观执行的全方位控制。
*   **强大的批量与群控能力**：可同时对海量海马云电脑或云手机实例下达指令，轻松实现同步操作、批量任务分发与状态监控，是效率倍增的核心引擎。
*   **复杂任务流自动化**：支持编排一系列连续操作，形成完整的自动化工作流。无论是“登录网站 -> 查询数据 -> 生成报告”还是“打开渲染软件 -> 加载文件 -> 开始渲染”，CAA都能让AI为您代劳。
*   **无缝AI集成**：基于标准的MCP协议，提供简洁稳定的API接口。只需简单的几步配置，即可将强大的云端执行能力赋予您现有或正在开发的大模型应用。

## **3. 工作原理**

1.  **准备云端环境**：在海马云平台开通并运行您的云电脑或云手机实例。
2.  **获取访问凭证**：登录CAA服务平台，创建应用并获取专属的API Key。
3.  **连接AI大脑**：将API Key集成至您所使用的大语言模型或AI应用中。
4.  **下达指令，自动执行**：通过您的AI应用下达任务指令（如“让A分组的所有云手机打开浏览器访问特定网页”），CAA服务将实时解析指令并驱动对应的海马云设备完成操作。

## **4. 典型应用场景**

*   **自动化测试与运维**：
    在数百台云手机上自动部署并执行APP兼容性测试、性能测试，实时收集日志与反馈。
*   **渲染农场智能调度**：
    根据渲染任务的优先级和资源需求，由AI自动分配和管理海马云电脑集群，实现7x24小时无人值守的高效渲染。
*   **社交媒体与内容自动化**：
    规模化、自动化地在云手机矩阵中执行内容发布、互动、数据采集等任务，极大提升运营效率。
*   **AI数字人与虚拟直播**：
    由大模型驱动数字人，并通过CAA服务在云电脑中实时操作直播软件，实现高度智能和自动化的直播互动。
*   **数据采集与处理**：
    控制云端设备集群，自动化访问不同数据源进行信息聚合与初步处理，为模型训练或商业分析提供支持。

## **5. 我们的愿景**

CAA不仅仅是一个工具，它是连接AI智能与云端算力的关键桥梁。我们相信，通过为AI赋予直接操控应用世界的能力，将催生出超乎想象的新应用与新业态。我们诚邀广大开发者和合作伙伴，加入腾讯MCP广场，体验CAA服务，共同探索AI驱动的云服务新纪元！

## **6. 操作步骤**

### 步骤 1：创建 API Key

1. 登录 [海马 CAA](https://caa.haimacloud.com/)
2. 在左侧导航栏中单击 "API Key 管理"。
3. 在服务管理页面上单击创建新的 API Key。
4. 在创建 API KEY 对话框中选择是云电脑、云手机，并单击确定。

### 步骤 2：获取 MCP 地址

在 "API Key 管理" 页面上，在目标 API KEY 的操作列中单击查看 MCP 地址。

### 步骤 3：完成 MCP 服务配置

在支持 MCP 的工具中添加 MCP 地址，并完成 MCP 服务配置。

#### CodeBuddy

点击 CodeBuddy 设置，进入MCP tab页，点击添加MCP，在打开的settings.json文件中添加如下内容：

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
        "Authorization": "Bearer <您的云手机API密钥>"
      }
    }
  }
}
```

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
        "Authorization": "Bearer <您的云手机API密钥>"
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
        "Authorization": "Bearer <您的云手机API密钥>"
      }
    }
  }
}
```
