# Streamable HTTP MCP Server

This is a quick sample for developing MCP server for mini PoC or demo purposes. It is not desinged for production systems. You can clone it into your local desktop for running, debungging, or enhancing. you can also deploy the mcp server application to Azure container instance for remote consumption into mcp clients. 

## Clone the repository

git clone https://github.com/mafzal786/mcp-server.git

## In Visual Studio Code - Run the MCP Server locally 
Run the following commands
```
cd mcp-server 
uv venv
uv sync
uv run mcpserver.py
```

## Run MCP Inspector to test and debug MCP Server
Open a new terminal window and run the following commands
```
npx @modelcontextprotocol/inspector
```

Open a browser and navigate to http://127.0.0.1:6274

In the URL enter: http://localhost:8001/mcp and click Connect. 


## Deploy to Azure Container Apps
Run the following commands
```
az containerapp up \
    --resource-group <RESOURCE_GROUP_NAME> \
    --name streamable-mcp-server \
    --environment mcp \
 	--location <REGION> \
    --source .
```

## Connect to remote MCP server in VS Code using Github Copilot
GitHub Copilot, in conjunction with the Model Context Protocol (MCP), can be utilized for testing an MCP server. This involves configuring Copilot Chat to interact with the local MCP server running the application under test.
For Github Copilot, modify the mcp.json on .vscode as below for example.

```json
{
	"servers": {
		"my-mcp-server-8f6eaae9": {
			"url": "http://localhost:8001/mcp",
			"type": "http"
		},
	
		
	},
	"inputs": []
}

```

## Steps for using Github Copilot for MCP Server testing
Run the MCP server locally: Start the application that is acting as the MCP server in a local environment such as in VS Code.<br>
**Access Copilot Chat:** Open Copilot Chat within your IDE (e.g., Visual Studio Code).<br>
**Enable Agent Mode:** Select "Agent mode" within the Copilot Chat prompt box.<br>
**Add the MCP Server Tool:**
<br>
1-Click the "Tools" button in Copilot Chat.<br>
2-Select "Add More Tools...".<br>
3-Choose "Add MCP Server".<br>
4-Specify the server type (e.g., HTTP or Server-Sent Events) and provide the relevant server details (e.g., URL).




    
<img width="332" height="864" alt="github copilot 1" src="https://github.com/user-attachments/assets/43a97b0d-e0d7-4b08-a077-08b248948607" />
