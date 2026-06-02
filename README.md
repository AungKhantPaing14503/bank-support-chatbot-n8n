# Bank Support Chatbot n8n Workflow

A Burmese/Myanmar-language customer support chatbot workflow built in n8n for bank support triage.

The chatbot can receive messages from webhook or Telegram, redact sensitive information, classify risk, create support ticket logs, and reply in Burmese/Myanmar language.

## Features

- n8n workflow-based chatbot
- Webhook support
- Telegram bot support
- Gemini AI model support
- Conversation memory
- Burmese/Myanmar customer replies
- OTP, PIN, password, card number, and account number redaction
- Risk classification
- Human escalation flag
- Support ticket logging

## Repository Structure

```text
bank-support-chatbot-n8n/
  README.md
  workflows/
    bank-support-chatbot-v2.json
``
How To Export From n8n
Open the workflow in n8n.
Click the workflow menu.
Choose Download or Export workflow.
Save the file as:
bank-support-chatbot-v2.json
Upload it to GitHub inside the workflows/ folder.
How To Import Into n8n
Download this repository from GitHub.
Open n8n.
Go to Workflows.
Choose Import from File.
Select:
workflows/bank-support-chatbot-v2.json
n8n will create a new workflow.
Required Credentials
After importing, reconnect these credentials manually:

Telegram Bot credential
Google Gemini API credential
Any n8n data table or database credential if required
Credentials and API keys are not included in this repository for security reasons.

Gemini Setup
Go to Google AI Studio.
Create a Gemini API key.
In n8n, open the Google Gemini Chat Model node.
Add or select your Gemini credential.
Paste the API key.
Save the credential.
Telegram Setup
Create a Telegram bot using BotFather.
Copy the bot token.
In n8n, open the Telegram trigger/reply nodes.
Add or select the Telegram credential.
Paste the bot token.
Save the credential.
Test Messages
Basic test:

hi
OTP safety test:

ကျွန်တော့် OTP က 123456 ပါ login ဝင်လို့မရဘူး
Expected result:

The OTP should be redacted.
contains_secret should be true.
secret_types should include otp.
risk_level should be high.
priority should be urgent.
The bot should reply in Burmese and tell the customer not to share OTPs.
Security Notes
Do not upload:

Gemini API keys
Telegram bot tokens
OpenAI API keys
Real customer data
Real bank account numbers
Real support ticket data
Keep the repository private if the workflow is still under development.

Workflow Purpose
This workflow is designed for customer support triage only. It should not perform real banking actions such as freezing cards, moving money, changing credentials, or verifying identity. High-risk cases should be escalated to a human support agent.
