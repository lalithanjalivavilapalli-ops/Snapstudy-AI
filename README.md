# 📚 SnapStudy AI

**Snap it. Understand it. Save it.**

SnapStudy AI is a Streamlit chat app that acts as a study buddy. Take a photo of a problem, diagram, or page of notes you don't understand (or just type a question) and Gemini explains it in plain language. When you're done, one click emails your study notes to you so they're saved outside the app.

## Features
- Chat with an AI study buddy using text and/or photos (Gemini vision)
- System prompt scoped to studying - politely declines off-topic questions
- Handles unreadable photos gracefully
- "Send to Email" button writes concise study notes and sends them via Gmail
- Secrets kept out of the repo (`secrets.toml.example` template only)

## Tech stack
Python · Streamlit · Google Gemini (`google-genai`) · Gmail SMTP (`smtplib`)

## Project structure
```
snapstudy-ai/
├── app.py                       # the app
├── prompts.py                   # the AI's personality and prompts
├── requirements.txt
├── .gitignore
└── .streamlit/
    └── secrets.toml.example     # template - copy to secrets.toml
```

## Run locally
1. Clone the repo and open the folder
2. Create and activate a virtual environment
   ```
   python -m venv venv
   source venv/bin/activate        # macOS/Linux
   .\venv\Scripts\Activate.ps1     # Windows PowerShell
   ```
3. Install dependencies
   ```
   pip install -r requirements.txt
   ```
4. Get a Gemini API key from [Google AI Studio](https://aistudio.google.com)
5. On the sending Gmail account, turn on 2-Step Verification, then create an App Password at [myaccount.google.com/apppasswords](https://myaccount.google.com/apppasswords)
6. Copy `.streamlit/secrets.toml.example` to `.streamlit/secrets.toml` and fill in your values
7. Run
   ```
   streamlit run app.py
   ```
   The app opens at http://localhost:8501

## Deploy (Streamlit Community Cloud)
1. Push this repo to GitHub (never commit `.streamlit/secrets.toml`)
2. Go to [share.streamlit.io](https://share.streamlit.io), sign in with GitHub, click **New app**
3. Pick the repo, branch, and `app.py`
4. In **Settings → Secrets**, paste the contents of your local `secrets.toml`
5. Deploy

## Live app
_Add your Streamlit URL here after deploying._
