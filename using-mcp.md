# Using Chrome DevTools MCP with Claude Code

## Setup Instructions

### 1. Install Visual Studio Code
Download and install from [code.visualstudio.com](https://code.visualstudio.com/)

### 2. Install Node.js (latest LTS version)
Download and install from [nodejs.org](https://nodejs.org/)

**Verify installation**: Open a terminal and run:
```
node --version
```
You should see the Node.js version number (e.g., `v20.11.0`)

### 3. Install Claude Code
```
npm install -g @anthropic-ai/claude-code
```

### 4. Create a Project Folder
```
mkdir my-claude-project
cd my-claude-project
```

### 5. Install Chrome DevTools MCP
```
claude mcp add chrome-devtools --scope project cmd /c npx -y chrome-devtools-mcp@latest
```

### 6. Open Folder in VS Code
Open the project folder in VS Code and confirm that a `.mcp.json` file exists in the folder.

### 7. Launch Claude Code
In the VS Code terminal, run:
```
claude
```

### 8. Verify MCP Installation
In the Claude input panel, type `/mcp` to verify the MCP server is installed and running.

### 9. Test Browser Automation
Try this prompt to test the Chrome DevTools MCP:
```
use chrome dev tool mcp and nav to anthropic website
```

## What Are These Tools?

**Visual Studio Code** is a free, open-source code editor from Microsoft that provides a rich development environment with extensions, debugging, and integrated terminal support.

**Claude Code** is Anthropic's official CLI tool that brings Claude AI assistant directly into your development workflow, allowing you to interact with Claude AI model through the command line to perform coding tasks, analyze code, and automate development activities.

**MCP (Model Context Protocol)** is an open standard that enables AI applications like Claude Code to securely connect to external data sources and tools, allowing Claude to interact with services beyond its built-in capabilities through a standardized interface.

**Chrome DevTools MCP** is an MCP server that exposes Chrome browser automation capabilities to Claude Code, enabling Claude to navigate websites, interact with web pages, take screenshots, analyze performance, inspect network requests, and perform browser-based testing tasks programmatically.

**How They Work Together**: VS Code provides the development environment, Claude Code runs as a CLI tool that you interact with, MCP serves as the communication protocol, and Chrome DevTools MCP extends Claude's abilities to control and inspect Chrome browser sessions for web automation and testing tasks.