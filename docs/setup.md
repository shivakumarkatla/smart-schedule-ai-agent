# Setup Notes

## Required credentials

Create credentials in n8n for:

- Telegram
- OpenAI
- Google Calendar
- Gmail

The public workflow export intentionally does not contain credential IDs or secrets.

## Google Calendar

The workflow expects the AI agent to provide `Start` and `End` values when calling the Google Calendar tool.

Set the calendar to your own calendar after importing the workflow.

## Gmail

The AI agent extracts:

- recipient
- subject
- message

from the user's request and passes those values to the Gmail tool.

## Telegram

The final AI Agent output is passed to the Telegram send-message node, so the user receives a concise confirmation in the same conversation.
