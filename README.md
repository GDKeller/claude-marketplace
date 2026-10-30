# gdkeller Claude Code marketplace

Grant Keller's personal [Claude Code plugin marketplace](https://code.claude.com/docs/en/plugins/marketplace-reference.md). This repo is only the catalog. Each plugin lives in its own repo unless it's small enough to live here.

## Install

From inside Claude Code:

```
/plugin marketplace add GDKeller/claude-marketplace
/plugin install board@gdkeller
```

Or from your shell:

```bash
claude plugin marketplace add GDKeller/claude-marketplace
claude plugin install board@gdkeller
```

## Plugins

| Plugin | Description | Source |
|---|---|---|
| `board` | Plain-text project management board for human-AI collaboration: tasks, epics, ADRs, notes, and references as Markdown files with YAML frontmatter | [GDKeller/board](https://github.com/GDKeller/board) (`plugin/`) |

## Adding a plugin

Add an entry to [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json):

- **Plugin in its own repo**: use a `git-subdir` source (or `github` if the plugin is the repo root).
- **Small plugin kept here**: put it in `plugins/<name>/` and use a relative source, `"source": "./plugins/<name>"`.

Keep `version` in the plugin's own `plugin.json`, not in the catalog entry. Then check the catalog:

```bash
claude plugin validate .
```
