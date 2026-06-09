# Email Automation

This project contains an n8n workflow export named `Email Automation.json`.

## Overview

This workflow automatically sends a welcome email whenever a new row is added to a Google Sheet, and then updates the same row to mark that the email was sent.

## How It Works

1. **Google Sheets Trigger**
   - Watches the configured Google Sheet for a new row event.

2. **If**
   - Validates that the `Email` column contains a valid email address.
   - Ensures the row has not already been marked as sent.

3. **Send a message**
   - Sends an email to the address from the sheet using Gmail.

4. **Update row in sheet**
   - Updates the same row and sets `Mail sent` to `Yes`.

## Prerequisites

Before importing and running this workflow, make sure you have:

- An n8n instance
- Google Sheets OAuth credentials
- Gmail OAuth credentials
- A Google Sheet containing at least these columns:
  - `Email`
  - `Mail sent`

## Setup Instructions

1. Open your n8n dashboard.
2. Import the file `Email Automation.json`.
3. Reconnect the required Google Sheets and Gmail credentials.
4. Confirm the Google Sheet ID and sheet name in the workflow nodes.
5. Activate the workflow.

## Notes

- The current email subject and body are set in the workflow as:
  - Subject: `Hello Gen AI devloper`
  - Message: `welcome to my wokflow`
- You can edit these values in the Gmail node if you want to customize the message.

## Purpose

This workflow is useful for automatically notifying people from a Google Sheet and tracking whether the email has already been sent.
