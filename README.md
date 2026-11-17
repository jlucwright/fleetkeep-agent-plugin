# Fleetkeep import review

Prepare a vehicle CSV for Fleetkeep and flag missing or ambiguous import values.

Published by Studea Limited. Product: [fleetkeep](https://fleetkeep.co.uk). Support: hello@fleetkeep.co.uk.

## Cline, VS Code and GitHub Copilot

[Installation commands, VS Code link and native Copilot configuration](clients/README.md). Browser OAuth and authorised product access are required.

## Gemini CLI

Review vehicles, maintenance and reminders in your Fleetkeep fleet.

```sh
gemini extensions install https://github.com/jlucwright/fleetkeep-agent-plugin --ref v1.0.1
```

Start Gemini CLI and use `/mcp auth fleetkeep` to sign in through the browser when needed. A Fleetkeep account with access to the requested records and the applicable service plan is required. Installation does not grant account access.

Run the auth command explicitly after installation. Automatic OAuth is disabled so the configured permission scopes are used. Gemini CLI 0.68.0 completed browser OAuth and a protected read with a fictional QA account on 17 November 2026. Gemini model authentication is separate; use a supported sign-in method or a Gemini API key. A billing-disabled Google project was used for these connection checks, with no model generation.

This Gemini extension uses `https://fleetkeep.co.uk/mcp` with an explicit read-only tool allowlist. It exposes `get_fleet_action_brief`, `search_vehicles`, `get_vehicle_action_detail`. The client and model service process the records you request under their data settings.

`gemini-extension.json` and `GEMINI.md` configure Gemini CLI. The existing Agent Plugin files and skills below retain their separate client-specific scope.

## Cursor and Agent Plugins installation

Import this Git repository as an Agent Plugin in Cursor or another compatible client. The package contains the `fleetkeep-import-review` skill. It has no install scripts, hooks, dependencies or bundled credentials. Material used with Cursor remains subject to the model service and account settings; this package does not upload it to Fleetkeep.

Cursor supports the root `plugin.json` Agent Plugins format. Use [Cursor’s plugin installation and management guidance](https://cursor.com/docs/plugins) for your account; an official Marketplace listing requires Cursor review. The community Cursor Directory listing is separate.

## Cursor skill scope

The Cursor and portable Agent Plugin configuration is skills-only. It does not install an MCP connection or sign in to the product. Prepare and review supplied material in the workspace, then use the product’s normal review flow for account changes. No live vehicle lookup, automatic import or paid account access is included.

## Package layout

`plugin.json` declares the portable Agent Plugins manifest. `skills/` contains the product-specific review workflow. See the skill for inputs, boundaries and an example.

MIT applies to these package files. Product names and service access remain subject to their respective terms.

`.plugin/plugin.json` repeats public metadata for Cursor Directory’s current indexer, which does not read the standard root manifest for listing metadata. The root manifest remains the portable runtime contract. Logo URLs reference existing company website icons.
