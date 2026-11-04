# AI Finance Tracker

AI finance tracker built with n8n and Gemini: Log expenses by sending a chat message. The workflow records the transaction, updates your balance in Google Sheets, and emails you when the balance runs low.

## 🎥 Demo
https://github.com/user-attachments/assets/ec0a7c50-c42a-4fa9-8f04-bf5be6fd83ea

## The Problem
Tracking expenses by hand is slow, and it's easy to forget to update the balance.

## How It Works
1. **Trigger:** a chat message is received (e.g. "Spent 450 on groceries")
2. **AI agent:** Google Gemini extracts the amount, category, and whether it's income or an expense, with simple memory for conversation context
3. **Get previous balance:** reads the last balance from Google Sheets
4. **Append row:** saves the date, amount, category, and new balance to the sheet
5. **Alert:** if the balance is 5,000 or below, Gmail sends a low-balance email

## Tools Used
n8n, Google Gemini, Google Sheets, Gmail

## Setup
1. Import `workflows/n8n-workflow.json` into n8n (Workflows > Import from File)
2. Connect your own credentials for Gemini, Google Sheets, and Gmail
3. Create a Google Sheet using the columns in `sample-data/sample-sheet.csv`
4. Replace the placeholders (`YOUR_SHEET_ID`, `YOUR_EMAIL`) in the nodes
5. Adjust the low-balance threshold (default 5,000) if needed

## Notes
Credentials and personal data have been removed. All sample data is fake.
