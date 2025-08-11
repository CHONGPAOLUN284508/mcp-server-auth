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


    
