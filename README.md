# Agent workspace

This repository is the working home for future bot development and documentation.

## Current status

The repository contains this project brief, Dr Eggbot and five specialist agent definitions, and a descriptive team manifest for on-demand delegation. Existing trading bot source code has not been supplied or imported. No persistent bot runtime or broker integration code is present.

## Project scope

Develop and document call and put analysis bots. For each implemented bot, document its purpose, data inputs, signal rules, outputs, and how to run it.

## Operating boundaries

- IBKR access must remain read-only unless the owner explicitly authorizes a change.
- Do not submit, modify, or cancel orders.
- Confirm available market data and permissions before claiming a live connection.
- Keep credentials, API tokens, account identifiers, positions, and other private account data out of this repository.

## Next step

Obtain the existing source code or define and implement new bots with the owner. Do not describe planned features as implemented or running.

## Command and agents

The President is the owner's sole command channel: delegates specialist work, reviews results, and reports with screenshots when available.

- [Dr Eggbot — Executive Assistant to the President](agents/dr-eggbot.md): designs and rewrites bots, performs healthchecks, and handles operations delegated by the President. Does not override orders or take over other bots' responsibilities.

The saved definition can be supplied to an agent for delegated work. It does not start a background service or connect to IBKR.

## Specialist team

| Role | Responsibility | Reports to |
| --- | --- | --- |
| [Call Analyst](agents/call-analyst.md) | Bullish/call research and countercase review | Dr Eggbot |
| [Put Analyst](agents/put-analyst.md) | Bearish/put research, hedges and countercase review | Dr Eggbot |
| [X Monitor](agents/x-monitor.md) | Read-only news verification and catalyst research | Dr Eggbot |
| [MediQ Growth Analyst](agents/mediq-growth.md) | Separate business research: customer fit, website clarity and service validation | Dr Eggbot |
| [Disk Steward](agents/disk-steward.md) | Scoped storage audits; explicitly delegated recoverable cleanup | Dr Eggbot |

[Team manifest](team.json) maps prompts and reporting relationships. For each task, the President delegates through Dr Eggbot with an objective, scope, constraints and acceptance criteria. Dr Eggbot routes market ideas for counterpart review and consolidates the result for the President. Neither analyst must recommend a trade. No device cleanup has been performed.

These definitions and the manifest are instructions, not technical permission enforcement, executable workers, a scheduler, or a background monitoring service. An available agent must be given the prompt and task for on-demand work.

## Observed IBKR tool capabilities

During this setup, read-only tool requests succeeded for watchlists, an underlying snapshot, expiry metadata, a bounded option chain, and call/put snapshots. Returned fields included bid/ask and sizes, last price and its timestamp, volume, option implied volatility and open interest, and aggregate option-volume fields.

This does not establish real-time entitlements: explicit real-time/delayed status and quote/open-interest timestamps were absent. Greeks and transaction-level flow, sweep detection, and buyer/seller classification were not available in the observed results. Aggregate volume is not verified directional flow. Each future analysis must recheck availability, freshness, entitlements and required evidence; unavailable inputs must not be fabricated. No private account details or quotes are stored here.

## X Monitor availability

[X Monitor](agents/x-monitor.md) is defined but unconnected and unscheduled. No suitable X-feed reading connection was found during setup. Public official releases can support delegated research, but are not access to the owner's X feed. It verifies original sources and timestamps, separates facts from opinions and rumors, and routes verified catalysts through Dr Eggbot to both analysts. It cannot post or change the X account. Saving its definition does not activate continuous monitoring.

## MediQ business research

[MediQ Growth Analyst](agents/mediq-growth.md) uses free public sources to assess website clarity, suitable customer segments and commercially testable service ideas. It has no IBKR access and cannot contact prospects, edit the website or purchase services without an explicit request. Regulatory scope must be confirmed before regulated services are launched. Private strategy and sensitive research results do not belong in this public repository.

A separate weekly review has been configured for Wednesdays at 09:00 Africa/Johannesburg, beginning September 16, 2026, with flexible scheduling. The saved role and manifest do not themselves execute that review or constitute a running service.
