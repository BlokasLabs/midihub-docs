# AI Tools

Midihub Editor can be used with desktop AI clients through MCP, a standard way for applications to interact with AI tools. You can let the Editor link supported tools automatically, or copy the manual MCP settings and paste them into your AI client yourself.

This enables you to inspect the current setup, understand how a preset works, and get help with routing, mappings, comments, port names, and processing pipelines. It can also be useful when you want to explore an idea before rebuilding it manually, refine a preset step by step, troubleshoot unexpected behavior, or try alternate versions of a preset for different instruments, songs, or setups.

## Setting Up AI Tools in Midihub Editor

Open Help -> Configure AI Tools...

The AI Tool Configuration dialog checks which supported desktop AI clients are installed on your computer and shows their current status.

The dialog also includes an "AI Tools Enabled" checkbox. The AI Tools toolbar button is shown only when AI Tools are enabled and either linked tools need an update or no tools are currently linked. To change the AI Tools setting, open Help -> Configure AI Tools...

Supported tools include:

- Claude Desktop
- Codex
- Cursor
- Gemini CLI
- VS Code
- Windsurf

The following statuses may appear:

- **Linked**: Midihub MCP entries are already configured.
- **Unlinked**: The tool was detected, but Midihub MCP is not configured yet.
- **Outdated**: Midihub MCP entries exist, but they need to be updated.
- **Not detected**: The tool was not found on this computer.

To configure a detected tool, click Link next to it. To configure all detected unlinked tools at once, click Link All.

If a tool already has an older Midihub MCP configuration, click Update All to refresh it.

To remove the Midihub MCP entries from a tool, click Unlink or Unlink All.

Before Midihub Editor changes a detected tool's MCP configuration, it creates a backup copy of the tool's existing settings file. If backup creation fails, the configuration update is aborted for that tool.

Some tools may need to be restarted after configuration changes. If so, the dialog will show a restart recommendation.

## Backup Location

Backup copies of tool settings files are stored in a Midihub Editor backup folder under the current user's local application data location.

| Platform | Backup location |
| -------- | --------------- |
| Windows | `%LOCALAPPDATA%\Blokas\Midihub Editor\mcp-backups` |
| macOS | `~/Library/Application Support/Blokas/Midihub Editor/mcp-backups` |
| Linux | `~/.local/share/Blokas/Midihub Editor/mcp-backups` |

Each backup file is saved with a timestamp and keeps the original file extension, so multiple backup copies can be kept for the same tool.

## Manual MCP Instructions

If your preferred AI client is not listed in the AI Tool Configuration dialog, click Manual Instructions...

The dialog shows these values:

- Midihub MCP Command: the local Midihub MCP launch command.
- Midihub MCP Extra Arguments: extra arguments for the Midihub MCP command. This field is shown on Linux only.
- Midihub Oracle MCP Command: the local Midihub Oracle MCP launch command.
- Midihub Oracle MCP Extra Arguments: extra arguments for the Midihub Oracle MCP command. This filed is shown on Linux only.

Use these values in your AI client's MCP configuration.

On Linux, configure the Midihub MCP command together with the Midihub MCP Extra Arguments value shown in the dialog.

In most cases, you should configure both:

- The Midihub MCP command for local Midihub Editor access.
- The Midihub Oracle MCP command for Midihub Oracle access.

Use the Copy buttons in the dialog to avoid typing the values manually.

## Using Midihub With Desktop AI Clients

After the MCP servers are configured in your desktop AI client, restart the client if needed and open a new conversation.

You can then ask the client to inspect the current Midihub setup, list available tools and resources, or help you build and edit presets.

If the AI client cannot see Midihub tools after configuration, check the status in Help -> Configure AI Tools...

## Linux

On Linux, Midihub Editor currently supports manual MCP configuration only.

Open Help -> Configure AI Tools... to view the Midihub MCP command, the Linux-only extra arguments, and the Midihub Oracle MCP command, then paste them into your AI client's MCP configuration.
