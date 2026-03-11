AI Social Media Content Automation (LinkedIn)
Overview

This project automates AI-powered LinkedIn content creation and posting.

The workflow reads article content, summarizes it using AI, generates a LinkedIn post, and automatically publishes it.

Built using n8n workflow automation and Google Gemini AI model.

Workflow Steps
1. Google Sheets Trigger

Create a Google Sheet to store article links or text.

Add Google Sheets Trigger Node in n8n.

The workflow starts when a new row is added.

2. Summarize Article Using AI

Add Basic LLM Chain Node.

Connect Google Gemini Chat Model.

The prompt summarizes the article into key insights.

Example Prompt
You are a social media strategist.

Analyze the article and create a summary:
1. Capture the 3 key insights
2. Include actionable advice
3. Maintain the original tone
4. Highlight implications for the audience
5. Keep it under 200 words

Article: {{$json.text}}
3. Generate LinkedIn Post

Add another LLM Chain Node.

Connect it to the summary node output.

Generate a professional LinkedIn post.

Example Prompt
Write a LinkedIn post discussing key AI industry insights.

Requirements:
- Professional tone
- Clear structure
- Industry analysis
- Encourage discussion
- Include a call to action
4. LinkedIn Developer App Setup

Create an app in **LinkedIn Developer Portal.

Steps

Go to LinkedIn Developer Apps

Click Create App

Enter:

App Name

Company Page

Logo

Enable APIs

Share on LinkedIn

Sign In with LinkedIn using OpenID Connect

5. OAuth Authentication

Configure authentication:

Copy Client ID

Copy Client Secret

Paste them into n8n LinkedIn credentials

Add OAuth Redirect URL from n8n to LinkedIn App settings.

6. Auto Post to LinkedIn

Add LinkedIn Node in the workflow.

Configuration

Operation → Create Post

Select LinkedIn account

Add generated text from the AI node

The workflow automatically publishes the post on LinkedIn.

Workflow Architecture
Google Sheets → AI Summary → LinkedIn Content Generator → LinkedIn Auto Post
Technologies Used

n8n – Workflow Automation

Google Gemini – AI Content Generation

**LinkedIn API – Social Media Posting

**Google Sheets – Data Trigger Source

Future Improvements

Multi-platform posting

Content scheduling

Analytics tracking

Multi-post automation
