# Trading bot workspace

This repository is the working home for future bot development and documentation.

## Current status

The repository contains this project brief and an agent definition for Dr Eggbot. Existing trading bot source code has not been supplied or imported. No runnable bots or verified broker integrations are present yet.

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
