# Puppeteer MCP Server

A Model Context Protocol (MCP) server that provides browser automation capabilities using Puppeteer. This server enables LLMs to interact with web pages, take screenshots, and execute JavaScript in a real browser environment with **anti-detection** capabilities.

## Features

- 🚀 **Browser automation** with Puppeteer
- 🛡️ **Anti-detection** using `puppeteer-extra-plugin-stealth`
- 🚫 **Ad blocking** with `puppeteer-extra-plugin-adblocker`
- 📸 **Screenshot capabilities** (PNG/JPEG formats)
- 💻 **JavaScript execution** in browser context
- 🍪 **Cookie management** (get/set cookies)
- 📝 **Console log monitoring**

## Tools

| Tool | Description |
|------|-------------|
| `puppeteer_navigate` | Navigate to a URL with optional launch options |
| `puppeteer_screenshot` | Capture screenshots of the page or specific elements |
| `puppeteer_click` | Click on elements using CSS selectors |
| `puppeteer_fill` | Fill input fields with text |
| `puppeteer_select` | Select options in dropdown elements |
| `puppeteer_hover` | Hover over elements |
| `puppeteer_evaluate` | Execute JavaScript in the browser context |
| `puppeteer_set_cookie` | Set cookies for a domain |
| `puppeteer_get_cookies` | Get all cookies for the current page |

## Resources

1. **Console Logs** (`console://logs`) - Browser console output
2. **Screenshots** (`screenshot://<name>`) - Captured screenshot images

## Installation

### NPX (Recommended)

```json
{
  "mcpServers": {
    "puppeteer": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-puppeteer"]
    }
  }
}
```

### Local Development

```bash
# Clone the repository
git clone https://github.com/ffffyhffff/puppeteer-mcp-server.git
cd puppeteer-mcp-server

# Install dependencies
npm install

# Build the project
npm run build
```

### Docker

```json
{
  "mcpServers": {
    "puppeteer": {
      "command": "docker",
      "args": [
        "run", "-i", "--rm", "--init",
        "-e", "DOCKER_CONTAINER=true",
        "mcp/puppeteer"
      ]
    }
  }
}
```

## Configuration

### Cursor IDE Configuration

Add to your `~/.cursor/mcp.json`:

```json
{
  "puppeteer": {
    "command": "node",
    "args": ["<path-to-project>/dist/index.js"],
    "env": {
      "PUPPETEER_EXECUTABLE_PATH": "C:/Program Files/Google/Chrome/Application/chrome.exe"
    }
  }
}
```

### Environment Variables

| Variable | Description |
|----------|-------------|
| `CHROME_PATH` | Path to Chrome/Chromium executable |
| `PUPPETEER_LAUNCH_OPTIONS` | JSON-encoded Puppeteer launch options |
| `ALLOW_DANGEROUS` | Allow dangerous browser args (default: false) |
| `DOCKER_CONTAINER` | Set to "true" when running in Docker |

## License

MIT License
