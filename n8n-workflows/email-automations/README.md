# Email Automation System (Parent + Sub Agent)

A multi-agent email automation system built in n8n where a parent 
agent intelligently decides whether to draft or send an email, 
delegating the sending task to a dedicated sub-agent.

## What It Does
- Creates Gmail drafts on command
- Sends emails through a dedicated sub-agent
- Parent agent handles decision-making
- Sub-agent handles execution

## How It Works
1. User sends a message via n8n chat interface
2. Parent Agent decides the intent (draft or send)
3. For drafts: Gmail Draft tool is called directly
4. For sending: Email Sending Tool triggers the Sub Agent workflow
5. Sub Agent uses its own AI and Gmail tool to send the email

## Architecture
Parent Agent
├── Create a draft in Gmail (direct tool)
└── Email Sending Tool
      └── Email Sub Agent (separate workflow)
            └── Send a message in Gmail

## Stack
- n8n
- OpenAI GPT-4.1 Mini
- Gmail API

## Files
- email-parent.json : Main workflow, import this first
- email-sub-agent.json : Sub agent workflow, import this second

## How To Use
1. Import email-sub-agent.json first into n8n
2. Then import email-parent.json
3. Connect your OpenAI and Gmail credentials in both workflows
4. Activate both workflows
5. Open the chat interface and start giving email commands
