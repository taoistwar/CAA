# **CAA (Control Any App) by Haima Cloud**

## **1. Project Overview**

CAA (Control Any App) is an innovative MCP (Model Context Protocol) service launched by **Haima Cloud**, a leading provider of cloud PC and cloud phone services.

We are dedicated to breaking down the barriers between large AI models and the ecosystem of cloud-based applications. With CAA, developers and enterprise users can obtain a powerful API key that seamlessly connects any large language model (LLM) to Haima Cloud's cloud PC and cloud phone instances. This means you no longer need complex scripts or manual intervention. Simply use natural language or simple code instructions to enable AI to control hundreds of cloud devices, performing complex tasks such as launching applications, rendering content, querying information, and batch operations—just like a human user—elevating automation and intelligence to a new level.

## **2. Core Features**

*   **Granular Application-Level Control**: Precisely start, stop, or operate specific applications (APPs) within cloud devices, enabling comprehensive control from macro-level scheduling to micro-level execution.
*   **Powerful Batch and Group Control**: Issue commands simultaneously to a vast number of Haima Cloud PCs or cloud phone instances, easily achieving synchronized operations, batch task distribution, and status monitoring—serving as the core engine for exponential efficiency gains.
*   **Complex Task Flow Automation**: Supports orchestrating a series of sequential operations into complete automated workflows. Whether it's "log in to a website -> query data -> generate a report" or "open rendering software -> load file -> start rendering," CAA enables AI to perform these tasks on your behalf.
*   **Seamless AI Integration**: Based on the standard MCP protocol, it provides a simple and stable API interface. With just a few configuration steps, you can empower your existing or in-development large model applications with powerful cloud execution capabilities.

## **3. How It Works**

1.  **Prepare the Cloud Environment**: Activate and run your cloud PC or cloud phone instances on the Haima Cloud platform.
2.  **Obtain Access Credentials**: Log in to the CAA service platform, create an application, and obtain a dedicated API key.
3.  **Connect the AI Brain**: Integrate the API key into your large language model or AI application.
4.  **Issue Commands and Automate Execution**: Issue task instructions through your AI application (e.g., "have all cloud phones in Group A open a browser and access a specific webpage"). The CAA service will parse the instructions in real time and drive the corresponding Haima Cloud devices to complete the operations.

## **4. Typical Use Cases**

*   **Automated Testing and Operations**:
    Automatically deploy and execute app compatibility and performance tests on hundreds of cloud phones, collecting logs and feedback in real time.
*   **Intelligent Rendering Farm Scheduling**:
    Allow AI to automatically allocate and manage Haima Cloud PC clusters based on rendering task priorities and resource requirements, enabling efficient, 7x24 hour unattended rendering.
*   **Social Media and Content Automation**:
    Scale and automate content publishing, engagement, and data collection tasks across a matrix of cloud phones, significantly enhancing operational efficiency.
*   **AI Avatars and Virtual Live Streaming**:
    Drive digital avatars with large models and use the CAA service to operate live streaming software in real time on cloud PCs, enabling highly intelligent and automated live interactions.
*   **Data Collection and Processing**:
    Control a cluster of cloud devices to automatically access different data sources for information aggregation and preliminary processing, supporting model training or business analytics.

## **5. Our Vision**

CAA is more than just a tool; it is the key bridge connecting AI intelligence with cloud computing power. We believe that by empowering AI with the ability to directly control the application world, entirely new applications and business models beyond imagination will emerge. We warmly invite developers and partners to join the Tencent MCP Square, experience the CAA service, and explore the new era of AI-driven cloud services together!

## **6. Procedure**

### Step 1: Create an API Key

1. Log in to [Haima CAA](https://caa.haimacloud.com/).
2. Click **API Key Management** in the left navigation panel.
3. On the service management page, click to create a new API Key.
4. In the "Create API Key" dialog box, select either Cloud PC or Cloud Phone, then click **OK**.

### Step 2: Obtain the MCP Address

On the **API Key Management** page, locate your target API Key and click **View MCP Address** in the Actions column.

### Step 3: Complete MCP Service Configuration

Add the MCP address in any tool that supports MCP, and complete the MCP service configuration.


#### CodeBuddy Integration

Click the CodeBuddy settings, go to the MCP tab, click "Add MCP", and add the following content to the opened settings.json file:

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
