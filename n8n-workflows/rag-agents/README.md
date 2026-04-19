# RAG Agent

An AI agent built in n8n with Retrieval-Augmented Generation (RAG) 
that answers questions from your own documents using Pinecone 
as the vector database.

## What It Does
- Answers questions from uploaded documents via Pinecone
- Sends emails through Gmail on command
- Uploads files to Google Drive
- Remembers conversation context using session-based memory

## How It Works
1. User sends a message via Webhook
2. AI Agent decides which tool to use
3. Pinecone is queried for relevant document chunks
4. Response is returned back to the user

## Stack 
- n8n
- OpenAI GPT-4.1 Mini
- Pinecone Vector DB (namespace: roadmap)
- Gmail API
- Google Drive API

## Files
- RAG.json : Import this into n8n to use the workflow

## How To Use
1. Import RAG.json into your n8n instance
2. Connect your OpenAI, Pinecone, Gmail and Google Drive credentials
3. Upload your documents to the watched Google Drive folder
4. Start the webhook and chat with your data
