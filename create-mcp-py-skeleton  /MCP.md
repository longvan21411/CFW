---
name: ${{ values.mcpName }}
version: 1.0.0
risk-tier: ${{ values.riskTier }}
---

# ${{ values.title }}

${{ values.description }}

## Tools

<!-- TODO: Document each tool your server exposes. One section per tool. -->

### `example-tool`

Echoes a message back to the caller.

**Input:**

| Parameter | Type | Required | Description |
|---|---|---|---|
| `message` | string | yes | The message to echo |

**Output:** The echoed message as plain text.

**Example:**

```json
{ "message": "hello" }
```

→ `"Echo: hello"`

## Usage

### Claude Code

Add this server to `.claude/settings.json`:

```json
{
  "mcpServers": {
    "${{ values.mcpName }}": {
      "url": "https://YOUR_ENDPOINT_HERE"
    }
  }
}
```

### Cursor

Add to `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "${{ values.mcpName }}": {
      "url": "https://YOUR_ENDPOINT_HERE"
    }
  }
}
```

## Risk tier: `${{ values.riskTier }}`

<!-- TODO: Document the specific risk implications of your server's tier. -->
