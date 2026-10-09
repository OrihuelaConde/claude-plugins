# OrihuelaConde's Claude Code plugins

A plugin marketplace for [Claude Code](https://code.claude.com/docs) that lists OrihuelaConde's plugins and mods. Each plugin lives in its own repository, with its documentation and license.

## Add the marketplace

To add the marketplace, run the following command in a terminal:

```bash
claude plugin marketplace add OrihuelaConde/claude-plugins
```

The command adds a marketplace named `orihuelaconde`. To install a plugin from it, run the following command:

```bash
claude plugin install PLUGIN@orihuelaconde
```

Replace `PLUGIN` with a name from the [plugin list](#plugins).

## Plugins

| Plugin | What it does |
| --- | --- |
| [cozy-clawd](https://github.com/OrihuelaConde/cozy-clawd) | An unofficial fan mod: a cozy pixel-art band above the prompt where Clawd acts out what Claude is doing, beside a scene of session meters. |
| [local-whisper](https://github.com/OrihuelaConde/local-whisper-mcp) | Skill for the Local Whisper MCP server, which transcribes audio and video with Whisper on your computer. Install the server from its [latest release](https://github.com/OrihuelaConde/local-whisper-mcp/releases/latest). |

## List a new plugin

To list a plugin, add an entry to `plugins` in `.claude-plugin/marketplace.json`, with the HTTPS address of the plugin's repository as its source:

```json
{
  "name": "PLUGIN",
  "source": { "source": "url", "url": "https://github.com/OrihuelaConde/REPOSITORY.git" },
  "description": "DESCRIPTION"
}
```

Replace `PLUGIN` with the `name` in the plugin's `.claude-plugin/plugin.json`, `REPOSITORY` with its repository, and `DESCRIPTION` with one line about what it does.

Use a `url` source with the HTTPS address, not a `github` source: on Windows, Claude Code clones a `github` source over SSH, so the install fails for anyone without an SSH key for GitHub.

Then check the file and push:

```bash
claude plugin validate .
```

People who already added the marketplace see the new plugin after they run `claude plugin marketplace update orihuelaconde`.
