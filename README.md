AI Social Media Content Automation (LinkedIn)
Overview

This project automates AI-powered LinkedIn content creation and publishing using workflow automation.

The system reads article content from Google Sheets, summarizes it using Google Gemini AI, generates a professional LinkedIn post, and automatically publishes it through the LinkedIn API.

The automation is built using n8n workflow automation, enabling a seamless pipeline from content input to social media publishing.

Key Features

Automated AI-powered article summarization

LinkedIn post generation with professional tone

Auto publishing to LinkedIn

Trigger-based workflow using Google Sheets

Fully automated content pipeline

Workflow Architecture
Google Sheets Trigger
        ↓
AI Article Summarization (Gemini)
        ↓
LinkedIn Post Generation
        ↓
LinkedIn API Auto Publishing
Workflow Steps
1. Google Sheets Trigger

A Google Sheet is used to store article content or links.

When a new row is added, the n8n workflow is automatically triggered.

Configuration

Create a Google Sheet

Add article text or link in a row

Connect the Google Sheets Trigger Node in n8n

2. Article Summarization using AI

The article content is summarized using the Google Gemini Chat Model through an LLM Chain Node.

Prompt Example

You are a social media strategist.

Analyze the article and create a summary:
1. Capture the 3 key insights
2. Include actionable advice
3. Maintain the original tone
4. Highlight implications for the audience
5. Keep it under 200 words

Article: {{$json.text}}
3. LinkedIn Post Generation

The summarized content is then used to generate a professional LinkedIn post.

Another LLM Chain Node processes the summary and converts it into a structured LinkedIn post.

Prompt Example

Write a LinkedIn post discussing key AI industry insights.

Requirements:
- Professional tone
- Clear structure
- Industry analysis
- Encourage discussion
- Include a call to action
4. LinkedIn Developer App Setup

To enable automated posting, a LinkedIn Developer App must be created.

Steps:

Go to LinkedIn Developer Portal

Click Create App

Enter required details:

App Name

Company Page

Logo

Enable APIs:

Share on LinkedIn

Sign in with LinkedIn using OpenID Connect

5. OAuth Authentication

Authentication is required for posting on behalf of a LinkedIn account.

Steps:

Copy Client ID and Client Secret from LinkedIn Developer App

Add them to n8n LinkedIn credentials

Add the OAuth Redirect URL from n8n into LinkedIn App settings

6. Auto Publish to LinkedIn

The final step automatically posts the generated content.

LinkedIn Node Configuration

Operation → Create Post

Select LinkedIn account

Use AI-generated content as the post text

Once the workflow runs, the post is automatically published to LinkedIn.

Technologies Used

n8n – Workflow automation platform

Google Gemini AI – Content summarization & generation

LinkedIn API – Social media publishing

Google Sheets – Data trigger source

Future Improvements

Multi-platform posting (Twitter, Instagram, Medium)

AI-powered content scheduling

Performance analytics tracking

Multi-post batch automation

Image generation for posts

Use Case

This system is ideal for:

Content creators

Digital marketers

AI enthusiasts

Social media managers

Businesses automating LinkedIn content

It reduces manual effort while maintaining consistent, high-quality social media content.
