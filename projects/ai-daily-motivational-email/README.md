# AI-Powered Daily Motivational Email Automation

## Overview

This project uses **n8n** to generate a motivational quote with an AI model and email it to a recipient list every day at **7:00 AM Africa/Lagos time**.

The recipient list is managed in Google Sheets, so recipients can be added or updated without rebuilding the workflow.

## Workflow

`Schedule Trigger → Message a Model → Google Sheets → Gmail`

1. **Schedule Trigger** starts the workflow on its daily schedule.
2. **Message a Model** generates a motivational quote.
3. **Google Sheets** provides the recipient information.
4. **Gmail** sends the email to the recipients.

## Tools Used

- n8n
- AI model integration
- Google Sheets
- Gmail
- Scheduled workflow automation

## Business Use Case

The workflow demonstrates how recurring communication can be automated to reduce manual work and deliver messages consistently. Similar patterns can be adapted for reminders, internal updates, customer follow-ups, and other routine business communications.

## Project Evidence

The following assets will be added when available:

- [ ] Exported n8n workflow JSON
- [ ] Screenshot of the completed workflow
- [ ] Screenshot of successful email delivery
- [ ] Short Loom walkthrough

## Notes

This is a learning and portfolio project. Credentials, API keys, recipient email addresses, and other private information must not be included in the repository.
