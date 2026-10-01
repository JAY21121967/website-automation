# Architecture

## Website Content Automation

The recommended production architecture is:

1. Google Sheets stores the content queue.
2. n8n reads a row whose status is `Ready`.
3. AI generates a structured article draft.
4. n8n prepares SEO metadata.
5. Telegram receives the draft for review.
6. A human approves or rejects the draft.
7. Approved content is published to WordPress.
8. Google Sheets is updated with the final status and URL.

## Why include human approval?

Automation should remove repetitive work without removing useful human control.

A practical workflow is:

**AI draft → human review → automated publishing**

This makes the system easier to audit and safer for client websites.
