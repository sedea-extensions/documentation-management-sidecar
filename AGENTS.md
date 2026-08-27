# documentation-management-sidecar — Sedea extension agent guide

Extension slug: `documentation-management-sidecar`

This repository is a **user bespoke Sedea extension** materialized from [`sedea-extensions/extension-template`](https://github.com/sedea-extensions/extension-template). It is **not** part of the Sedea application monorepo (`sedea-ai/app/extensions/` shipped natives).

## Verify before ship

```bash
npm run verify
```

Runs lint → typecheck → compile → test from the repo root.

## Extension Development Host (EDH)

Open this folder in Sedea and use the checked-in `.vscode/launch.json` to launch Extension Development Host smoke. Develop against **this repo root** — not `sedea-ai/app/extensions/`.

## Extension MCP contribution

Author `sedea.mcp-contribution.json` using `sedea.mcp-contribution.schema.json` and `sedea.mcp-contribution.example.json`.

- Top-level **required** keys: `extensionId`, `version`, `servers`
- Each server declares **`transport`**: `stdio` or `sse`
- **Scaffold does not register runtime MCP** — **Install Sedea Extension** registers on packaged Sedea after VSIX ship

Project rules: `.cursor/rules/sedea-mcp-contribution.mdc`

## Sedea MCP Hub appendix

**sedea-mcp-hub** is for **external REST/API bridges only** — not extension-native stdio/SSE MCP. Extension MCP belongs in the contribution manifest → install mission → `extensionContributions`.

## Post-scaffold delivery

After scaffold, enter **Software Development `plan and deliver`** **in this user extension repo** for feature work and VSIX ship.

1. Open Mission Control in Sedea with **this repo** as the workspace (or add this folder to the workbench).
2. Start dispatch: **`plan and deliver`** (Software Development center).
3. Do **not** use **Scaffold New Sedea Extension** for ongoing feature implementation — that mission is develop-track entry only.
4. Produce the installable artifact with **`npm run package`** (vsce) → `{publisher}.{name}-{version}.vsix` at the extension repo root (or documented `dist/`). **Install Sedea Extension** consumes that `.vsix` on packaged Sedea — scaffold does not produce or install it.

Handoff contract: terminal scaffold output on the sedea lane ends at promote-and-close; Software Development ship chain runs on this repo via `coding-session`.

## maintain extension template

When platform conventions drift, operators run sedea center mission **`maintain extension template`** on the hosting stack — not ad-hoc edits to the canonical template without that mission.
