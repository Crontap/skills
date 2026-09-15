# Crontap Agent Skills

These Agent Skills teach coding agents how to manage Crontap scheduled HTTP
jobs, uptime monitors, and heartbeats. They prefer the Crontap MCP server and
use the public REST API only when MCP is unavailable and the account has Ultra
API access.

## Install

Install the production collection:

```bash
npx skills add Crontap/skills
```

Install from a local checkout of this monorepo:

```bash
npx skills add ./skills
```

The skills CLI selects the correct installation locations for supported
agents. Run `npx skills add --help` for current agent and installation options.

## Catalogue

- `crontap-quickstart`
- `crontap-schedule-http-job`
- `crontap-natural-language-schedules`
- `crontap-heartbeat-for-cron`
- `crontap-uptime-monitor`
- `crontap-debug-failed-runs`
- `crontap-retries-and-idempotency`
- `crontap-replace-vercel-cron`
- `crontap-replace-github-actions-cron`
- `crontap-supabase-edge-function-cron`
- `crontap-ai-built-apps`
- `crontap-recurring-agent-endpoint`

## Contributing

Keep every skill self-contained and validate changes from the repository root:

```bash
npm run test:skills
```

Use tool names and input fields from `shared/mcp/toolManifest.ts` and
`shared/mcp/toolInputs.ts`. Bump `metadata.version` when instructions change.
Never include live credentials or secret ping URLs in examples.

## Publishing

Changes under `skills/` are synced to the public
[`Crontap/skills`](https://github.com/Crontap/skills) repository after they
reach the monorepo's `main` branch. The public repository keeps the
`skills/<name>/SKILL.md` layout used by the skills CLI and skills.sh.

The source repository secret `API_TOKEN_GITHUB` must contain a fine-grained
GitHub personal access token restricted to the `Crontap/skills` repository with
Contents read and write permission. Do not grant access to other repositories
or additional permissions.

License: [MIT](LICENSE).
