# Setup Guide

This repository documents the project; it does not include an importable n8n workflow JSON file.

## Prerequisites

- An n8n account
- A Telegram bot created with BotFather
- A Telegram chat that has started the bot (send `/start` to it)
- An exchange-rate API or data source that provides the three values you want to send

## Configuration outline

1. Create a **Schedule Trigger** and set it to run daily at **8:00 AM**.
2. Add the HTTP Request or other data-source node(s) needed to retrieve your exchange rates.
3. Inspect the node output and identify the exact JSON field for each of the three rate values.
4. Add or configure the Telegram **Send a text message** node.
5. In the message Text field, use n8n's expression picker to insert each rate value. Put each value on a separate line.
6. Select the correct Telegram credential and target chat ID.
7. Execute a test run and confirm the three values arrive correctly in Telegram.
8. Save and activate/publish the workflow in n8n.
9. Confirm the workflow timezone so the schedule runs at the intended local time.

## Security

- Store the Telegram bot token in n8n credentials; do not hardcode it into a URL or message body.
- Keep API keys and other secrets in credentials or a secure secret store.
- Never commit bot tokens, API keys, passwords, private chat IDs, or credential exports to a public repository.
- If a live bot token is exposed, revoke it with BotFather and replace it.

## Troubleshooting

- **Telegram says “chat not found”:** confirm the chat ID is correct and send `/start` to your bot from the target Telegram account.
- **Rates are missing:** inspect the previous node's output and map the actual rate fields using the expression picker.
- **All rates appear on one line:** insert line breaks in the Telegram Text field between each rate.
- **No scheduled message arrives:** confirm the workflow is active/published, the schedule timezone is correct, and the last execution has no errors.
