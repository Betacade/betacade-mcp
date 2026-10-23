# Betacade MCP server

Playtest your web game from your coding agent. Deploy a web build (Unity WebGL, Godot, HTML5), get a
link anyone can play in the browser, then ask what happened: who played, how far they got, what
broke, what they said, and which bugs to fix next.

The server is hosted; there is nothing to install or run. It's at **`https://api.betacade.com/mcp`**
(Streamable HTTP). Your agent signs you in with OAuth the first time, and your studio role decides
what it can do. A read-only connection can't change anything.

## Connect

**Claude Code**

```sh
claude mcp add --transport http betacade https://api.betacade.com/mcp
```

**VS Code**: [Install in VS Code](https://insiders.vscode.dev/redirect/mcp/install?name=betacade&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.betacade.com%2Fmcp%22%7D), or

```sh
code --add-mcp '{"name":"betacade","type":"http","url":"https://api.betacade.com/mcp"}'
```

**Cursor**: [Add to Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=betacade&config=eyJ1cmwiOiJodHRwczovL2FwaS5iZXRhY2FkZS5jb20vbWNwIn0=)

**Anything else**: add a remote (HTTP) MCP server with the URL above.

## Tools

| Tool | What it does |
|---|---|
| `list_games` | The games you can reach, your role on each, and its play link |
| `create_game` | Make a game |
| `start_build`, `finish_build` | Deploy a build: upload its files, then put it live |
| `deploy_files`, `edit_files`, `get_files` | No shell (a chat)? Deploy a small build with its files in the call, change one by sending only the edits, and read or search a build |
| `game_settings` | Builds, who may play each, saves and replays |
| `who_played` | A game's testers: sessions, play time, errors, how far they got |
| `session_evidence` | One tester's sessions: errors with stacks, console, feedback, replays |
| `list_bugs`, `update_bug` | The issue board; move a bug along as you fix it |

## More

- The full guide for agents: https://api.betacade.com/llms.txt
- Docs: https://api.betacade.com/docs
- Help: [Discord](https://discord.gg/DNmPcNxm6S) or hello@betacade.com
- [Privacy](https://betacade.com/privacy.html) · [Terms](https://betacade.com/terms.html)

This repository holds the server's listing (`server.json` for the
[MCP Registry](https://registry.modelcontextprotocol.io)), not its code.
