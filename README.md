 Sales-and-Support-AI-Agent
An n8n-based AI agent that answers customer questions, checks availability, and books appointments for a salon &amp; spa business powered by a self-updating knowledge base and automated follow-up emails.
 Salon & Spa AI Agent

An AI-powered sales and support agent built on n8n that handles customer conversations, answers business questions, checks appointment availability, books clients directly into the calendar, and follows up automatically after each visit.

 Overview

This agent acts as a 24/7 virtual receptionist for a salon and spa business. It combines a conversational AI agent with a live knowledge base, calendar integration, and automated email follow-ups : removing the need for staff to manually handle repetitive enquiries and bookings.

 Key Features

- Answers FAQs : responds to questions about services, pricing, and policies using a self-updating knowledge base.
- Checks real-time availability : queries the business calendar before confirming any appointment.
- Books appointments : creates the event directly in Google Calendar once a slot is confirmed.
- Conversation memory : maintains context across a chat session for natural, multi-turn conversations.
- Automated follow-ups : sends a personalised email to clients after their appointment is completed.
- Self-updating knowledge base : automatically re-indexes whenever new documents are added to Google Drive, so answers stay current without manual work.

 How It Works

The system is split into three connected n8n workflows:

 Workflow  Purpose 

 WF1 : Knowledge Base Loader;  Watches Google Drive for new/updated files, extracts and splits the text, and stores it as embeddings in a Supabase vector store. 
 WF2 : Chat & Booking Agent;  The core AI agent. Handles the live conversation, retrieves answers from the knowledge base, checks calendar availability, and creates bookings. 
 WF3 : Follow-up Messages; Runs on a schedule, loops through recent calendar events, and sends a follow-up email to each client. 

 Tech Stack

- n8n : workflow orchestration
- Google Gemini / OpenRouter : conversational LLM
- Supabase : vector store (knowledge base) and Postgres database (chat memory, bookings)
- Google Drive : source documents for the knowledge base
- Google Calendar : availability checks and booking creation
- Gmail : automated client follow-ups

 Who This Is For

Any appointment-based service business : salons, spas, clinics, studios  that wants to reduce time spent on repetitive enquiries and manual booking, while still giving clients fast, accurate responses at any hour.

 Setup

1. Import the three workflows into your n8n instance.
2. Connect credentials for Google Drive, Google Calendar, Gmail, Supabase, and your chosen LLM provider.
3. Point the Knowledge Base Loader at the Google Drive folder containing your business documents.
4. Create the required Supabase tables (vector store + bookings).
5. Publish all three workflows.

 Status

Actively in use 
