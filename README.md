# The Automation Digest – AI Weekly Newsletter Automation

## Overview

The AI Weekly Newsletter Automation is an end-to-end n8n workflow that automatically researches industry news, selects the most relevant stories, generates a professional newsletter using AI, personalizes each email, and distributes it to subscribers. The workflow eliminates the repetitive work involved in creating weekly newsletters while maintaining quality, consistency, and relevance.

Designed for media companies, marketing agencies, consultants, SaaS businesses, and content creators, this automation transforms raw news articles into a polished newsletter with minimal human involvement. Multiple AI models work together to classify stories, write engaging summaries, humanize the final content, and prepare HTML emails ready for delivery.

---

## Features

- Runs automatically on a scheduled basis
- Fetches the latest news from an external news source
- Filters stories by a target niche
- Prevents duplicate newsletter content
- Uses AI to classify story relevance
- Automatically excludes low-value articles
- Generates a complete newsletter draft
- Humanizes AI-generated writing for better readability
- Formats the newsletter into responsive HTML
- Personalizes every email with subscriber greetings
- Sends newsletters through Gmail
- Logs published stories to prevent future duplicates
- Automatically notifies the client if no qualifying stories are found

---

## Workflow

### 1. Scheduled Execution

The workflow begins on a predefined schedule, allowing newsletters to be generated automatically every week without manual intervention.

### 2. News Collection

An HTTP Request retrieves the latest news articles from an external news API. If no articles are returned, the workflow immediately sends a notification email and safely stops execution.

### 3. Story Selection

A custom code node filters articles based on the chosen niche before combining them with previously published stories stored in Google Sheets. Duplicate stories are automatically removed, ensuring subscribers never receive the same news twice.

### 4. AI Story Classification

A LangChain AI Agent evaluates each remaining article and determines whether it should be included in the newsletter. The AI considers factors such as relevance, usefulness, quality, and audience interest before making its decision. Only approved stories continue through the workflow.

### 5. Newsletter Generation

Approved stories are combined into a single dataset and passed to another AI Agent, which generates a complete newsletter containing engaging headlines, summaries, and logical organization.

A second AI Agent then humanizes the writing, improving readability and creating a more natural editorial tone while preserving factual accuracy.

### 6. HTML Formatting

A JavaScript node converts the finalized newsletter into responsive HTML suitable for email delivery across desktop and mobile email clients.

### 7. Subscriber Distribution

The workflow retrieves the subscriber list from Google Sheets, adds personalized greetings to each email, and sends the completed newsletter through Gmail.

### 8. Record Keeping

Every published article is logged in Google Sheets to prevent duplicate coverage in future newsletters. Additional notification emails are automatically sent if no new qualifying stories are available for publication.

---

## Technologies Used

- n8n
- Google Gemini
- Anthropic Claude
- OpenAI
- LangChain AI Agents
- Gmail
- Google Sheets
- HTTP Request API
- JavaScript Code Nodes

---

## Benefits

- Eliminates manual newsletter production
- Saves hours of weekly research
- Prevents duplicate story publication
- Produces consistently high-quality newsletters
- Personalizes every subscriber email
- Automatically handles edge cases and failures
- Maintains a historical archive of published stories
- Scales easily for growing subscriber lists
- Reduces content creation workload through AI

---

## Ideal Use Cases

This workflow is ideal for:

- Marketing agencies
- SaaS companies
- AI newsletters
- Technology publications
- Business consultants
- Investment newsletters
- Industry associations
- Content creators
- Research organizations

---

## Workflow Summary

Schedule Trigger → Fetch News → Validate Data → Select Niche Stories → Retrieve Published History → Remove Duplicate Stories → AI Classification → Filter Approved Stories → Build Newsletter → Humanize Content → Generate HTML → Retrieve Subscribers → Personalize Emails → Send Newsletter → Log Published Stories → Send Status Notifications

By combining automated news aggregation, AI-powered editorial review, intelligent content generation, and personalized email delivery, this workflow creates a fully automated newsletter production pipeline that consistently delivers fresh, high-quality content to subscribers while requiring little to no manual effort.
