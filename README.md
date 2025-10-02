# QA Test Automation Framework with Claude Code

An automated QA testing framework powered by Claude Code and Chrome DevTools MCP that enables natural language test script execution with intelligent script enhancement capabilities.

## Overview

This project provides a QA test automation framework where test scripts are written in plain natural language and executed by an AI-powered QA agent. The framework uses Chrome DevTools MCP for browser automation and continuously enhances test scripts with technical hints for faster, more reliable future executions.

## How It Works

### Core Components

1. **QA Script Executor Agent**: An AI agent configured to act as an elite QA automation engineer that:
   - Reads test scripts written in natural language
   - Executes each step using Chrome DevTools MCP
   - Enhances the original test scripts with technical hints after successful execution
   - Generates concise test execution reports

2. **Test Scripts**: Natural language test scripts stored in `/scripts` folder that define:
   - Test goals and scope
   - Pre-requisites and authentication details
   - Step-by-step test instructions
   - View mode (desktop/mobile)

3. **Chrome DevTools MCP**: Enables browser automation capabilities allowing the QA agent to:
   - Navigate to websites
   - Interact with web elements
   - Take snapshots
   - Verify application behavior

4. **Test Reports**: Generated in `/reports` folder after test execution with:
   - Pass/fail status for each step
   - Execution timestamp and duration
   - Issues encountered and resolutions
   - Test coverage summary

### The Enhancement Loop

One of the key features is the **in-place script enhancement** process:

1. The QA agent executes a test step from a natural language script
2. After successful execution, it appends technical hints to the original script
3. Example: `"click on login button"` becomes `"click on login button (hint: link element with text 'Login', uid typically ends in _7)"`
4. Future test runs become faster and more reliable as scripts accumulate these technical details

### Workflow

```
User writes test script → Claude Code invokes QA Agent → Agent reads script →
Executes steps via Chrome MCP → Enhances original script with hints →
Generates test report → User reviews results
```

## Project Structure

```
.
├── .claude/
│   ├── agents/
│   │   └── qa-script-executor.md    # QA agent configuration
│   └── settings.local.json           # Local Claude Code settings
├── scripts/
│   ├── template.md                   # Test script template
│   └── *.md                          # Test scripts
├── reports/
│   └── test-report-*.md              # Generated test reports
├── CLAUDE.md                         # Project instructions for Claude
├── using-mcp.md                      # Setup guide for Chrome DevTools MCP
└── README.md                         # This file
```

## Getting Started

### Prerequisites

1. **Visual Studio Code**: Download from [code.visualstudio.com](https://code.visualstudio.com/)
2. **Node.js (LTS)**: Download from [nodejs.org](https://nodejs.org/)
3. **Claude Code**: Install globally via npm
   ```
   npm install -g @anthropic-ai/claude-code
   ```

### Setup

1. Clone or navigate to this project folder
2. Install Chrome DevTools MCP:
   ```
   claude mcp add chrome-devtools --scope project cmd /c npx -y chrome-devtools-mcp@latest
   ```
3. Open the project in VS Code
4. Launch Claude Code in the terminal:
   ```
   claude
   ```
5. Verify MCP is running: Type `/mcp` in Claude Code

### Creating a Test Script

1. Copy `/scripts/template.md` to create a new test script
2. Define your test goal, view mode, pre-requisites, and auth details
3. Write test steps in natural language (e.g., "Navigate to login page", "Enter username and password")
4. Save the file in `/scripts` folder

### Running Tests

In Claude Code, instruct the QA agent to execute your test:

```
Please execute the test script at scripts/my-test-script.md
```

The agent will:
- Read your test script
- Execute each step using Chrome automation
- Enhance the script with technical hints
- Generate a test report in `/reports`

### Example Test Script

```markdown
## Software QA Test

Goal: Verify user can successfully log in and access chat functionality

view mode: desktop view

Pre-reqs: User account exists in the system

auth: username: testuser@example.com and password: TestPass123

Steps:
1. Navigate to the application homepage
2. Click on login button
3. Enter username and password
4. Click submit
5. Verify user is redirected to chat page
6. Verify chat interface loads correctly
```

## Key Features

- **Natural Language Testing**: Write tests in plain English, no coding required
- **Intelligent Enhancement**: Scripts become more precise with each execution
- **Browser Automation**: Full Chrome DevTools integration for web app testing
- **Automated Reporting**: Detailed test reports generated automatically
- **Living Documentation**: Test scripts serve as both executable tests and technical documentation

## Technology Stack

- **Claude Code**: AI-powered CLI assistant from Anthropic
- **MCP (Model Context Protocol)**: Standard protocol for AI-tool integration
- **Chrome DevTools MCP**: Browser automation server for Claude Code
- **Node.js**: Runtime for MCP servers

## Contributing

Test scripts and agent configurations can be modified to suit specific testing needs. The QA agent behavior is defined in `.claude/agents/qa-script-executor.md` and can be customized.

## License

This is a testing framework project. Refer to your organization's guidelines for usage and licensing.
