# Content Automation Workflow

This document explains the tested n8n workflow that generates website articles with AI, creates WordPress drafts, sends Telegram notifications, and updates the original Google Sheets row.

---

## 1. Project Overview

The workflow automates the preparation of website articles while keeping a human approval step before publication.

The workflow uses:

- n8n
- Google Sheets
- AI content generation
- WordPress
- Telegram

The content topic and primary keyword are entered into Google Sheets. n8n retrieves rows marked `Ready`, generates the article, creates a WordPress draft, sends the draft link through Telegram, and updates the original spreadsheet row.

---

## 2. Problem Being Solved

Preparing website content manually involves several repetitive steps:

1. Selecting an article topic
2. Writing the article
3. Formatting the content
4. Creating the WordPress draft
5. Notifying the person responsible for review
6. Recording the WordPress URL
7. Updating the content tracking sheet

This workflow connects these steps into one automated process.

The goal is not to automatically publish every AI-generated article. Instead, the workflow prepares the article and sends it for human review.

---

## 3. Workflow Architecture

```text
Google Sheets
     |
     v
Schedule Trigger
     |
     v
Get row(s) in sheet
     |
     v
IF: status = Ready
     |
     v
Message a model
     |
     v
Create a WordPress Draft
     |
     v
Send a Telegram Notification
     |
     v
Update Original Google Sheets Row
