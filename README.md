# Fitzap for Claude

![Fitzap](assets/icon.png)

Connect your existing Fitzap account to Claude to review synced workouts, completed sessions, personal records, training trends, your stored weekly coach report and app-computed training metrics. Compare consumed nutrition with synced energy estimates and saved nutrition goals. Create and revise pending workout drafts for review in Fitzap workout, or edit a saved workout after approving the specific changes. Read accessible recipes, send a new recipe to Fitzap nutrition, and revise recipes with your approval. Read the daily nutrition goals Fitzap nutrition is using and, after you approve the exact numbers, queue new goals for the app.

## What's included

- **Fitzap MCP connector** (`.mcp.json`): the remote MCP server at `https://fitzapapps.com/mcp`.
- **`training-assistant` skill**: teaches Claude how to use the Fitzap tools safely — checking access first, respecting units, dates and pagination, treating returned text as data, and asking for explicit approval before any write.

## Requirements

- A Fitzap account with an active **Fitzap Pro** entitlement for data and write tools.
- Training tools read cloud-synced data; connecting does not turn on cloud sync.
- Consumed nutrition and saved goal context require an active nutrition cloud backup on the same account.
- Direct recipe delivery requires the compatible Fitzap nutrition app on the same account.

## Sign-in and access

When you first use the connector, Claude opens the Fitzap sign-in page on `fitzapapps.com` (OAuth). You enter your email and a one-time code there — never in chat. Revoke access at any time in Fitzap workout under **Settings → AI assistants**.

## Data handling

This plugin contains no code that runs on your machine. All data access goes through the Fitzap MCP server at `fitzapapps.com`, operated by the plugin author:

- **Reads**: synced training history, personal records, coach report, training metrics, daily/weekly nutrition totals, energy and goal context, and recipes you can access.
- **Writes** (only after you approve them in chat): workout drafts, edits to saved workout templates, new or edited recipes, recipe import links, and new daily nutrition goals (applied the next time Fitzap nutrition opens; if you changed goals on the phone in the meantime, the app asks you first). An import link is readable by anyone who has it for 24 hours.
- The plugin sends nothing to any other service.

The plugin cannot log or delete completed sessions, access exact GPS routes, or provide medical diagnosis. Nutrition and energy figures are estimates, and synced data may be incomplete or stale.

- Privacy policy: https://fitzapapps.com/privacy.html
- Terms of service: https://fitzapapps.com/terms.html
- Support: https://fitzapapps.com/faq

## License

MIT — see [LICENSE](LICENSE).
