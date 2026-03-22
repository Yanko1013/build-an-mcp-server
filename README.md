# build-an-mcp-server

[MCP](https://modelcontextprotocol.io/docs/develop/build-server#typescript)

use in Cursor:

1. run:

    ```shell
    npm install
    npm run build
    ```

2. set .cursor/mcp.json:

    ```json
    {
      "mcpServers": {
        "weather": {
          "type": "stdio",
          "command": "node",
          "args": ["/ABSOLUTE_PATH/build-an-mcp-server/build/index.js"]
        }
      }
    }
    ```

3. Go to: Cursor - Preferences - Cursor Settings - MCP, enable weather.
