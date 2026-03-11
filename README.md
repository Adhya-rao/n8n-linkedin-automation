🚀 AI Social Media Content Automation (LinkedIn)
📌 Overview

This project automates AI-powered LinkedIn content creation and publishing.

The workflow reads article content from Google Sheets, summarizes it using Google Gemini AI, generates a professional LinkedIn post, and automatically publishes it using the LinkedIn API.

The automation is built using n8n workflow automation, enabling a seamless pipeline from content input to social media publishing.

⚙️ Workflow Steps
1️⃣ Google Sheets Trigger

Create a Google Sheet to store article links or text.

Add a Google Sheets Trigger Node in n8n.

The workflow starts automatically when a new row is added.

2️⃣ Summarize Article Using AI

Add a Basic LLM Chain Node.

Connect the Google Gemini Chat Model.

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
3️⃣ Generate LinkedIn Post

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
4️⃣ LinkedIn Developer App Setup

Create an app in the LinkedIn Developer Portal.

Steps

Go to LinkedIn Developer Apps

Click Create App

Enter the following details:

App Name

Company Page

Logo

Enable the APIs:

Share on LinkedIn

Sign in with LinkedIn using OpenID Connect

5️⃣ OAuth Authentication

Configure authentication for LinkedIn API.

Steps:

Copy Client ID

Copy Client Secret

Paste them into n8n LinkedIn credentials

Add the OAuth Redirect URL from n8n to LinkedIn App settings

6️⃣ Auto Post to LinkedIn

Add a LinkedIn Node in the workflow.

Configuration

Operation → Create Post

Select LinkedIn account

Add the AI-generated text

The workflow automatically publishes the post to LinkedIn.

🔄 Workflow Architecture
Google Sheets
      ↓
AI Article Summary (Gemini)
      ↓
LinkedIn Content Generator
      ↓
LinkedIn Auto Post
🛠 Technologies Used

n8n – Workflow Automation

Google Gemini – AI Content Generation

LinkedIn API – Social Media Posting

Google Sheets – Data Trigger Source

🚀 Future Improvements

Multi-platform posting

Content scheduling

Analytics tracking

Multi-post automation
