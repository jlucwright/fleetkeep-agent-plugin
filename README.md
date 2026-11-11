# Fleetkeep import review

Prepare a vehicle CSV for Fleetkeep and flag missing or ambiguous import values.

Published by Studea Limited. Product: [fleetkeep](https://fleetkeep.co.uk). Support: hello@fleetkeep.co.uk.

## Install

Import this Git repository as an Agent Plugin in Cursor or another compatible client. The package contains the `fleetkeep-import-review` skill. It has no install scripts, hooks, dependencies or bundled credentials. Material used with Cursor remains subject to the model service and account settings; this package does not upload it to Fleetkeep.

Cursor supports the root `plugin.json` Agent Plugins format. Use [Cursor’s plugin installation and management guidance](https://cursor.com/docs/plugins) for your account; an official Marketplace listing requires Cursor review. The community Cursor Directory listing is separate.

## Scope

This is a skills-only package. It does not install an MCP connection or sign in to the product. Prepare and review supplied material in the workspace, then use the product’s normal review flow for account changes. No live vehicle lookup, automatic import or paid account access is included.

## Package layout

`plugin.json` declares the portable Agent Plugins manifest. `skills/` contains the product-specific review workflow. See the skill for inputs, boundaries and an example.

MIT applies to these package files. Product names and service access remain subject to their respective terms.

`.plugin/plugin.json` repeats public metadata for Cursor Directory’s current indexer, which does not read the standard root manifest for listing metadata. The root manifest remains the portable runtime contract. Logo URLs reference existing company website icons.
