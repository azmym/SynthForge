# Contributing to SynthForge

Thanks for your interest. SynthForge is a curated marketplace, so contributions usually fall into one of three buckets:

1. Listing a new plugin you have built.
2. Improving an existing entry's metadata (description, tags, category).
3. Improving the marketplace itself (docs, automation, community files).

## 1. Listing a new plugin

### Step 1: Open a "Propose plugin" issue

Use the [Propose a plugin](./ISSUE_TEMPLATE/propose-plugin.yml) template and include:

- Plugin name and one-line summary.
- Public GitHub repo URL.
- What it ships: subagents, hooks, skills, slash commands, MCP servers.
- Why a Claude Code user would install it.
- License (must be OSI-approved).
- A tagged release on the plugin repo (so `/plugin marketplace update` resolves cleanly).

A maintainer will respond, ask any follow-up questions, and approve or request changes.

### Step 2: Open a PR adding the entry

Once approved, edit [`.claude-plugin/marketplace.json`](../.claude-plugin/marketplace.json) and append your entry to the `plugins` array. Minimum shape:

```json
{
  "name": "your-plugin",
  "source": {
    "source": "github",
    "repo": "your-org/your-plugin"
  },
  "description": "One sentence on what it does and who it helps.",
  "category": "ai-assistance",
  "tags": ["short", "scannable", "lowercase"],
  "keywords": ["matches", "what", "users", "search"]
}
```

Keep `description` under ~140 characters. It shows up in search and listings.

The full schema reference is in the [Claude Code marketplace docs](https://code.claude.com/docs/en/plugin-marketplaces#plugin-entries).

### Quality bar

Before we merge, we check that the plugin repo has:

- A clear README with install and usage instructions.
- At least one tagged release.
- An OSI-approved license file (MIT, Apache-2.0, BSD, etc.).
- No hardcoded secrets, surprise telemetry, or hostile defaults.
- Subagents/hooks/skills that follow Claude Code conventions.

We also look for naming that is descriptive, lowercase, and free of trademarks you do not own.

## 2. Updating an existing entry

Open a PR directly. Mention in the description what changed and why. If you are not the plugin's maintainer, please tag them in the PR.

## 3. Improving the marketplace itself

Docs, examples, automation, issue templates, accessibility, all welcome. Open an issue first if it is a structural change so we can align before you write code.

## Local checks

Before opening a PR, validate the manifest is well-formed JSON:

```bash
python -m json.tool .claude-plugin/marketplace.json > /dev/null
```

If you have `jq`:

```bash
jq . .claude-plugin/marketplace.json > /dev/null
```

## Code of Conduct

By participating you agree to follow our [Code of Conduct](./CODE_OF_CONDUCT.md). Be kind, be specific, assume good intent.

## Questions

Open a [Question](./ISSUE_TEMPLATE/question.yml) issue. We try to respond within a few days.
