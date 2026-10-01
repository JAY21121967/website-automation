# Setup Guide

## 1. Install n8n

Use either:

- n8n Cloud
- self-hosted n8n

## 2. Create credentials

Configure credentials inside n8n rather than storing secrets in GitHub.

Typical credentials:

- Google Sheets
- WordPress
- Telegram
- AI provider
- SMTP/email

## 3. Import a workflow

In n8n:

1. Open **Workflows**
2. Select **Import from File**
3. Choose a JSON file from `workflows/`
4. Open each node and configure its credentials
5. Replace placeholder URLs and IDs
6. Test with sample data
7. Activate only after the complete workflow has been tested

## 4. Google Sheets structure

Example columns:

| topic | keyword | status | wp_url | published_at |
|---|---|---|---|---|
| Website automation | website automation | Ready | | |

Suggested statuses:

- Ready
- Draft
- Approved
- Published
- Failed

## Security

Never put these in GitHub:

- API keys
- passwords
- WordPress application passwords
- Telegram bot tokens
- SMTP passwords
- private webhook URLs
