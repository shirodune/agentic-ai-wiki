# Agentic AI Wiki

This repository separates two responsibilities:

- Wiki maintenance: research, provenance, synthesis, and pages under `content/`.
- Publishing infrastructure: Quartz, verification, CI, and deployment.

See `AGENTS.md` for agent ownership boundaries and publication rules.

## Status

Quartz v5 publishing infrastructure is installed. Wiki research and substantive
content belong to the separate wiki-maintenance session.

## Commands

```bash
npm ci
npm run install-plugins
npm run check
npm test
npm run build
npm run verify:publication
```

`verify:publication` performs a fresh build and is the required deployment gate.
Only a genuine YAML Boolean `publish: true` is public. Quoted strings are private.
Non-Markdown assets are currently forbidden under `content/` because Quartz can
emit assets independently of page filters; request an infrastructure change if
public image or document support is needed later.

No Git remote or deployment hostname is configured yet.
