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

## List a new plugin

To list a plugin, add an entry to `plugins` in `.claude-plugin/marketplace.json`, with the plugin's repository as its source:

```json
{
  "name": "PLUGIN",
  "source": { "source": "github", "repo": "OrihuelaConde/REPOSITORY" },
  "description": "DESCRIPTION"
}
```

Replace `PLUGIN` with the `name` in the plugin's `.claude-plugin/plugin.json`, `REPOSITORY` with its repository, and `DESCRIPTION` with one line about what it does. Then check the file and push:

```bash
claude plugin validate .
```

People who already added the marketplace see the new plugin after they run `claude plugin marketplace update orihuelaconde`.
