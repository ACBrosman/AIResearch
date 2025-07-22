# AI Infosec Feed

This is a custom InfoSec feed using AI to prioritize cybersecurity risks relevant to your unique environment. This solution is self-hosted, automatically collects news from reputable sources, intelligently filters content by technologies like AWS and CrowdStrike, and employs a local AI model to produce summarized, actionable insights. This daily email digest delivers critical vulnerability alerts and recommendations to enable a more proactive security posture.

More information here: https://brocyber.com/building-a-personalized-infosec-feed-with-ai

## Requirements to Run InfoSec Digest Script

### Dependencies to Install
```bash
pip install feedparser tqdm ollama
```

### Prerequisites
1. **Ollama installed locally** with `llama3` model:
   ```bash
   # Install Ollama (varies by OS)
   ollama pull llama3
   ```

2. **Gmail App Password** (not regular password):
   - Enable 2FA on Gmail account
   - Generate app-specific password in Google Account settings
   - Replace `GMAIL_PASSWORD` in script

### Setup Steps
1. **Install dependencies** above
2. **Update email config** in script:
   - Change `GMAIL_SENDER` and `GMAIL_RECIPIENT` 
   - Replace `GMAIL_PASSWORD` with your Gmail app password
4. **Customize the technology to your infrastructure**
5. **Run the script**: `python infosec_digest.py`

### What It Does
- Fetches security news from RSS feeds (last 2 days)
- Filters for keywords (AWS, Azure, vulnerabilities, etc.)
- Uses local Ollama to summarize articles
- Generates HTML email digest with risk rankings
- Sends email and saves local HTML file

**Note:** Requires internet connection and Ollama running locally. First run may be slower as it processes articles through the AI model.


