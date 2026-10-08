# ${{ values.title }} — Getting Started

This project was scaffolded from the backBurner **Create a New MCP Server** template.

## Add your implementation

1. Install the MCP Python SDK (FastMCP):
   ```
   pip install fastmcp
   ```

2. Create `src/server.py` and implement your server:
   ```python
   from mcp.server.fastmcp import FastMCP

   mcp = FastMCP("${{ values.mcpName }}")

   @mcp.tool()
   def my_tool(param: str) -> str:
       """What the tool does."""
       return f"Result: {param}"

   if __name__ == "__main__":
       mcp.run()
   ```

3. Update `MCP.md` with real tool descriptions and usage examples.

4. Update `catalog-info.yaml` with the deployed endpoint URL once the server is running.

5. Register the server in the MCP Registry using the **Bring Your Own MCP Server** workflow.

## Reference

- [FastMCP](https://github.com/jlowin/fastmcp)
- [MCP Python SDK](https://github.com/modelcontextprotocol/python-sdk)
- [MCP specification](https://modelcontextprotocol.io)
