# Daily Exchange Rate Telegram Automation

A scheduled n8n workflow that sends three configured exchange-rate values to Telegram every morning.

## What it does

- Runs on a daily schedule configured for **8:00 AM**.
- Retrieves the configured exchange-rate data.
- Formats the three values on separate lines for easy reading.
- Sends the formatted update to a Telegram chat.

> The actual currency pairs and rates depend on the data source configured in the n8n workflow. This project is for informational purposes and is not financial advice.

## Workflow overview

1. **Schedule Trigger** — starts the workflow at the configured time.
2. **Exchange-rate data step(s)** — obtain the three rate values from the configured source.
3. **Message formatting** — maps the returned values into a readable Telegram message, with each rate on its own line.
4. **Telegram delivery** — sends the formatted message to the selected chat.

See [Workflow Overview](docs/WORKFLOW.md) for the high-level flow and [Setup Guide](docs/SETUP.md) for configuration notes.

## Example Telegram message

```text
Hello, here are today's exchange rates:

Rate 1: [value]
Rate 2: [value]
Rate 3: [value]

Have a nice day.
```

The labels and values should be adapted to match the currency pairs returned by your chosen data source.

## Built with

- n8n for workflow orchestration and scheduling
- An exchange-rate API or data source
- Telegram for message delivery

## Setup and security

This repository contains documentation only. **The n8n workflow JSON is intentionally not included.**

To recreate the workflow, follow [the setup guide](docs/SETUP.md). Configure secrets inside n8n credentials or another secure secret store. Do not commit bot tokens, API keys, passwords, private chat information, or credential exports.

## Testing and activation

The Telegram message was tested successfully, including formatting the three rates on separate lines. The schedule is configured for 8:00 AM; confirm the workflow is **Active/Published** in n8n and verify its timezone before relying on automatic daily runs.

## Limitations

- The rates are only as accurate and current as the selected data provider.
- Availability, API limits, and rate definitions depend on that provider.
- This repository does not contain the live workflow export or secrets.

## Author

**Iniobong Udom**  
GitHub: [@IniobongUdom7](https://github.com/IniobongUdom7)
