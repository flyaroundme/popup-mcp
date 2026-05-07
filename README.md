# popup-mcp

**Native GUI popups via MCP** - Display interactive popup windows from AI assistants through the Model Context Protocol.

Create rich dialogue trees with form elements (text, sliders, checkboxes, dropdowns, multiselect) and cascading conditional branches that adapt based on user selections.

## Installation

Unfortunately you need cargo to do that (get cargo as a part of rust installer here: https://rustup.rs/)

```bash
# Clone and install
git clone git@github.com:flyaroundme/popup-mcp.git
cd popup-mcp
cargo install --path crates/popup-gui
```

## Install in OpenCode

Add it to your OpenCode MCP config. Depending on your local setup, edit either:
- ~/.config/opencode/opencode.json
- or your local OpenCode config under ~/.opencode/
Add this MCP entry:
```
{
  "mcp": {
    "popup": {
      "type": "local",
      "command": ["popup"]
    }
  }
}
```
If popup is not available on your PATH, use the full path instead:
```
{
  "mcp": {
    "popup": {
      "type": "local",
      "command": ["/Users/YOUR_USER/.cargo/bin/popup"]
    }
  }
}
```
Restart OpenCode after saving the config. The popup MCP tool should then be available for native GUI popups.
Note: for this project, OpenCode should run `popup` with no extra arguments because MCP server mode is the default.


## Setup with Claude Desktop

```bash
# Add MCP server
claude mcp add popup --scope user -- popup --mcp-server

# Restart Claude Desktop
```

The `popup` tool will be available for creating GUI interactions.

## Quick Example

```bash
# Test a simple popup
echo '{"title": "Hello", "elements": [{"text": "World!"}]}' | popup --stdin

# Try example files
popup --file examples/simple_confirm.json
```

## Documentation

For complete documentation including JSON schema, element types, conditional visibility, templates, and examples:

**[Full Documentation](https://tidepool.leaflet.pub/3mcbegnuf2k2i)**

## Contributing

See `CLAUDE.md` for development guidance.

## License

MIT
