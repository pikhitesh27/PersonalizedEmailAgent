# Personalized Email Outreach App

This application helps you automate personalized email outreach to potential learners or clients. You can upload a list of users with their LinkedIn URLs, and the app will:
- Scrape each user's public LinkedIn profile
- Generate a personalized email draft for each user
- Let you review, download, and send these emails directly via your Gmail account

## Features
- Upload an Excel file with user details and LinkedIn URLs
- Enter course or offering details and a target persona
- Securely enter your Gmail credentials (credentials are never stored)
- Scrape LinkedIn profiles using the Bright Data API and generate custom email drafts for each user
- Download all results as a CSV
- Send emails to all users with a single click, with detailed logging for each step
- UI never resets during sending, and all results/logs are visible after actions

## Tech Stack
- Streamlit (user interface)
- Bright Data API (for LinkedIn scraping)
- Anthropic Claude API (for generating personalized emails)
- pandas (for Excel file handling)
- Supabase or MongoDB (for storing results, if configured)

## Getting Started
1. Clone this repository and install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
2. Create a `.env` file in the project root with your API keys and database credentials. Example:
   ```env
   ANTHROPIC_API_KEY=your_claude_api_key
   SUPABASE_URL=your_supabase_url
   SUPABASE_KEY=your_supabase_key
   BRIGHTDATA_API_KEY=your_brightdata_api_key
   ```
3. Run the app:
   ```bash
   streamlit run main.py
   ```

## Usage
1. Enter your course details and the persona you want to target.
2. Upload an Excel file with at least one column containing LinkedIn profile URLs (and, optionally, email addresses).
3. Enter your Gmail credentials (Gmail App Password recommended).
4. Start the workflow. The app will scrape LinkedIn profiles using the Bright Data API and generate email drafts.
5. Review the results, download the CSV, and send emails directly from the app.

## Security
- Your Gmail credentials are only used in-memory for the session and never stored.
- Use a Gmail App Password for sending emails (see Google instructions).
- Your Bright Data API key is required for LinkedIn scraping and should be kept secure in your `.env` file.
- For production use, consider setting up OAuth for Gmail.

## Troubleshooting
- Make sure your Gmail credentials and Bright Data API key are correct.
- If scraping fails, check your Bright Data API key, quota, or network connection.
- If emails are not sending, ensure your Gmail App Password is valid and you have not hit sending limits.

