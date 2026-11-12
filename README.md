# Replit Gemini Extension

Create and manage Replit apps from natural-language prompts directly in the
[Gemini CLI](https://github.com/google-gemini/gemini-cli).

The extension connects Gemini CLI to Replit through Replit's hosted MCP server.
A Replit account is created during MCP authentication if you do not already
have one.

## Requirements

- [Gemini CLI](https://github.com/google-gemini/gemini-cli) installed.
- A working internet connection.
- A browser for the Replit OAuth sign-in and authorization flow.

## Installation

Install the extension from this repository:

```bash
gemini extensions install https://github.com/replit/replit-gemini-extension
```

Restart Gemini CLI after installation. To confirm that Gemini CLI recognizes
the extension, run:

```text
/extensions list
```

## Authentication

When you first use a Replit tool, Gemini CLI will start the MCP authentication
flow. Follow the browser prompt to sign in to Replit and authorize access.

The extension requests these Replit OAuth scopes:

- `apps:read` — read Replit app information.
- `apps:write` — create and update Replit apps.

Review the requested permissions before approving access.

## Usage

Ask Gemini CLI in natural language. The extension provides three tools:

| Tool | What it does | Example request |
| --- | --- | --- |
| `create_app_from_prompt` | Creates a new Replit app from a description. | "Build a habit tracker with reminders." |
| `update_app_using_prompt` | Updates an app created during the current conversation. | "Add dark mode to the app we just created." |
| `ask_question` | Asks Replit Agent about an app without changing it. | "Explain how this app stores user data." |

For updates and questions, the app's `replId` must be available from the
creation response. If it is not available in the current conversation, provide
the relevant Replit app ID.

## Managing the extension

Update to the version declared by the extension:

```bash
gemini extensions update replit
```

List installed extensions:

```bash
gemini extensions list
```

Uninstall the extension:

```bash
gemini extensions uninstall replit
```

After installing, updating, enabling, or disabling an extension, restart the
Gemini CLI session when needed for the changes to take effect.

## Links

- [Replit](https://replit.com)
- [Gemini CLI extensions documentation](https://geminicli.com/docs/extensions/)
- [Report an issue](https://github.com/replit/replit-gemini-extension/issues)

## License

This project is licensed under the [MIT License](LICENSE).
