# Security Policy

## Supported scope

SynthForge itself is a manifest repository: it ships [`.claude-plugin/marketplace.json`](../.claude-plugin/marketplace.json) and documentation. The actual plugin code lives in each plugin's own GitHub repo.

- **Issues with the marketplace manifest, this repo's docs, or its workflows**: report here.
- **Issues with a specific plugin's code (`gemini-plugin`, etc.)**: report on that plugin's own repo. Each listed plugin is responsible for its own security policy.

## Reporting a vulnerability

Please do not open a public issue for security problems.

Instead, use one of:

1. [GitHub private vulnerability reporting](https://github.com/azmym/SynthForge/security/advisories/new) on this repo.
2. Direct message to [@azmym](https://github.com/azmym).

Include:

- A description of the issue and its impact.
- Steps to reproduce.
- The commit, tag, or version where you observed it.
- Any proof-of-concept (please be conservative about what you share publicly).

## Response expectations

- Acknowledgement within 72 hours.
- A triage assessment within 7 days.
- Coordinated disclosure once a fix is available, with credit to the reporter unless they prefer to remain anonymous.

## What counts

Examples of in-scope issues for this repo:

- A malformed `marketplace.json` that lets a hostile entry impersonate another plugin.
- A workflow that leaks secrets or runs untrusted code.
- A documentation link that points to a known-malicious resource.

Out of scope here (file with the plugin instead):

- Bugs or vulnerabilities inside a listed plugin's subagents, hooks, skills, or commands.
