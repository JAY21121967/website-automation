# Website Automation

A practical website automation project built around **n8n, WordPress, Google Sheets, AI, Telegram, and webhooks**.

The goal is to reduce repetitive website and marketing tasks by connecting content creation, approval, publishing, lead capture, and follow-up workflows.

## What this project demonstrates

- AI-assisted website content generation
- WordPress publishing automation
- Google Sheets as a simple content/lead database
- Telegram approval workflow
- Website lead capture with webhooks
- Automated email follow-up
- Error handling and retry concepts
- API-based integrations

## Architecture

```text
Google Sheets
     │
     ▼
   n8n
     │
     ├──► AI Content Generation
     │         │
     │         ▼
     │     Telegram Approval
     │         │
     │         ▼
     │      WordPress
     │
     └──► Lead Capture Webhook
               │
               ▼
          Google Sheets
               │
               ▼
          Email Follow-up
```

## Repository structure

```text
website-automation/
├── README.md
├── .gitignore
├── LICENSE
├── workflows/
│   ├── content-generation-template.json
│   ├── lead-capture-template.json
│   └── wordpress-publishing-template.json
├── prompts/
│   ├── article-generation.md
│   ├── seo-content.md
│   └── social-post.md
├── docs/
│   ├── architecture.md
│   └── setup.md
└── screenshots/
    └── .gitkeep
```

## Main workflow

### 1. Content automation

```text
Google Sheets
   ↓
Get topic
   ↓
AI generates article
   ↓
AI generates SEO metadata
   ↓
Send draft to Telegram
   ↓
Human approval
   ↓
Publish to WordPress
   ↓
Update Google Sheets
```

The approval step is intentional: AI prepares the content, while a human controls publication.

### 2. Lead automation

```text
Website form
   ↓
n8n Webhook
   ↓
Validate lead
   ↓
Google Sheets / CRM
   ↓
Send notification
   ↓
Follow-up sequence
```

## Important setup notes

The JSON files in this repository are **templates**. Before using them in production, configure your own:

- n8n credentials
- WordPress credentials/API access
- Google Sheets credentials
- Telegram bot credentials
- AI provider credentials
- SMTP/email credentials
- Webhook URLs

Never commit API keys, passwords, tokens, cookies, or `.env` files.

## Example use cases

- Automatically prepare WordPress blog posts
- Generate SEO article drafts
- Notify a business owner when a website lead arrives
- Store leads in Google Sheets
- Send scheduled follow-ups
- Automate social media content preparation
- Connect website forms with CRM or email systems

## Tech stack

- n8n
- WordPress
- Google Sheets
- Telegram
- Webhooks
- REST APIs
- AI APIs
- JavaScript

## Author

**Jay**

Web Developer & AI Automation Specialist

Website: https://varahiai.com/

GitHub: https://github.com/JAY21121967

## Disclaimer

This repository contains reusable examples and templates. Review every workflow, credential, API permission, and message before deploying it for a real business.
