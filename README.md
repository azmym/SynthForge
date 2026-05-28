# SynthForge

A Claude Code plugin marketplace for AI-augmented developer tooling.

## Add the marketplace

```bash
/plugin marketplace add azmym/SynthForge
```

## Available plugins

| Plugin | Description | Source |
|---|---|---|
| **gemini-plugin** | Gemini-as-second-opinion: validator, challenger, researcher, summarizer subagents + 6 auto-trigger hooks + 8 task-oriented skills | [azmym/gemini-plugin](https://github.com/azmym/gemini-plugin) |

## Install a plugin

```bash
/plugin install gemini-plugin@synthforge
```

## Update plugins

```bash
/plugin marketplace update synthforge
```

## How marketplace updates work

Each plugin entry in `.claude-plugin/marketplace.json` points to its own GitHub repository. When a plugin author publishes a new release (via a tag bump in the plugin's `plugin.json`), users running `/plugin marketplace update synthforge` get the new version. The marketplace itself only changes when we add or remove plugins.

## Contributing a plugin

1. Open an issue describing the plugin (purpose, components, repo URL).
2. After approval, submit a PR adding an entry to `.claude-plugin/marketplace.json`.
3. Each entry needs at minimum `name`, `source`, and `description`.

Plugin entries follow the [Claude Code marketplace schema](https://code.claude.com/docs/en/plugin-marketplaces#plugin-entries).

## License

MIT
