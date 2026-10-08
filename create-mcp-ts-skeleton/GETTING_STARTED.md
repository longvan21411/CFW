# ${{ values.title }} — Getting Started

This project was scaffolded from the backBurner **Create a New MCP Server** template.

## Add your implementation

1. Install the MCP TypeScript SDK:
   ```
   npm install @modelcontextprotocol/sdk zod
   npm install -D typescript tsx @types/node
   ```

2. Create `src/index.ts` and implement your server:
   ```ts
   import { McpServer } from "@modelcontextprotocol/sdk/server/mcp.js";
   import { StdioServerTransport } from "@modelcontextprotocol/sdk/server/stdio.js";
   import { z } from "zod";

   const server = new McpServer({ name: "${{ values.mcpName }}", version: "1.0.0" });

   server.tool("my-tool", "What the tool does", { param: z.string() }, async ({ param }) => ({
     content: [{ type: "text", text: `Result: ${param}` }],
   }));

   await server.connect(new StdioServerTransport());
   ```

3. Update `MCP.md` with real tool descriptions and usage examples.

4. Update `catalog-info.yaml` with the deployed endpoint URL once the server is running.

5. Register the server in the MCP Registry using the **Bring Your Own MCP Server** workflow.

## Reference

- [MCP TypeScript SDK](https://github.com/modelcontextprotocol/typescript-sdk)
- [MCP specification](https://modelcontextprotocol.io)
