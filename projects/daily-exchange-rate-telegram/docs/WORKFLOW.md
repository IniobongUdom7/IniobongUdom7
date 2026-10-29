# Workflow Overview

## Purpose

Send three configured exchange-rate values to Telegram on a daily schedule.

## High-level flow

```text
Schedule Trigger (8:00 AM)
        ↓
Fetch exchange-rate data
        ↓
Map/format the three rate values
        ↓
Telegram: Send a text message
```

This diagram describes the workflow's intended structure at a high level. Node names and API response fields may differ in the live n8n workflow.

## Message formatting

Each rate should be placed on its own line in the Telegram message text. In n8n, insert line breaks between the text and each mapped value; use the expression picker to select the correct field from the previous node's input.

## Important

The workflow JSON is intentionally not included in this repository. Refer to the live workflow in n8n for its exact node configuration and data source.
