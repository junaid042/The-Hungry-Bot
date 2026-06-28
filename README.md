# 🍳 The Hungry Bot

**An AI agent that turns your kitchen ingredients into real recipes, step-by-step instructions, a shopping list, and calorie estimates.**

🔗 **Live Demo:** [MariamMemon.pythonanywhere.com](http://mariammemon.pythonanywhere.com)

Built as a capstone project for **Google's 5-Day AI Agents Intensive: Vibe Coding Course**, hosted by Kaggle.

---

## The Problem

Every day, millions of people open their fridge and ask the same question: *"What can I actually make with this?"*

Searching recipe websites is time-consuming, and results rarely match exactly what you have at home. This leads to food waste, repetitive meals, and unnecessary grocery trips.

---

## The Solution

The Hungry Bot is an AI-powered concierge agent that acts as your personal kitchen assistant. You tell it what ingredients you have — it handles everything else.

**What it does:**
-  Searches the web in real time to find 2-3 relevant recipes using your ingredients
-  Generates clear step-by-step cooking instructions for each recipe
-  Builds a shopping list of missing ingredients automatically
-  Estimates calories per serving for each recipe
-  Scores how well each recipe matches your available ingredients (evaluation layer)

---

## Architecture

```
User (Browser)
      │
      ▼
Flask Backend (Python)
      │
      ├── Gemini API (google-genai SDK)
      │         │
      │         ├── Google Search Grounding Tool (real-time recipe search)
      │         ├── Recipe Generation & Instructions
      │         ├── Missing Ingredients Analysis
      │         ├── Calorie Estimation
      │         └── Relevance Scoring (Evaluation Layer)
      │
      ▼
HTML / CSS / JavaScript Frontend
      │
      ▼
Deployed on PythonAnywhere (free tier)
```

**Tech Stack:**

| Layer | Technology |
|---|---|
| Backend | Python, Flask |
| AI / Reasoning | Google Gemini API with Search Grounding |
| Frontend | HTML, CSS, JavaScript |
| Deployment | PythonAnywhere |
| Built with | Google Antigravity (Vibe Coding) |

---

## Course Concepts Demonstrated

| Concept | Where |
|---|---|
| Tool Use (Google Search Grounding) | Backend — Gemini API call with search tool |
| Evaluation Layer (Relevance Scoring) | Backend — `app.py` scoring function |
| Security (API key handling) | `.env` file, never exposed in frontend |
| Deployability | Live at MariamMemon.pythonanywhere.com |
| Built with Antigravity | Entire project built via vibe coding |

---

## Setup Instructions

### Prerequisites
- Python 3.10+
- A free Gemini API key from [Google AI Studio](https://aistudio.google.com)

### Steps

**1. Clone the repository**
```bash
git clone https://github.com/MariamMemon/the-hungry-bot.git
cd the-hungry-bot
```

**2. Create a virtual environment**
```bash
python -m venv venv
venv\Scripts\activate        # Windows
source venv/bin/activate     # Mac/Linux
```

**3. Install dependencies**
```bash
pip install -r requirements.txt
```

**4. Set up your API key**
```bash
cp .env.template .env
```
Open `.env` and replace the placeholder with your actual Gemini API key:
```
GEMINI_API_KEY=your_actual_key_here
```

**5. Run the app**
```bash
python app.py
```

Visit `http://127.0.0.1:5000` in your browser.

---

## How to Use

1. Type an ingredient into the input box (e.g. "chicken") and press **Enter** or click **Add**
2. Add as many ingredients as you have at home
3. Click **Find Recipes**
4. The agent will return 2-3 recipes with full instructions, a shopping list, calorie estimates, and a relevance score

---

## Security Notes

- The Gemini API key is stored in a `.env` file on the server only
- `.env` is excluded from this repository via `.gitignore`
- The API key is never sent to or exposed in the browser or frontend code
- Use `.env.template` to set up your own key safely

---

## Deployment (PythonAnywhere)

This app is deployed on PythonAnywhere free tier. To reproduce:

1. Upload the project files to PythonAnywhere via the Files tab
2. Create a virtual environment: `mkvirtualenv --python=python3.10 myenv`
3. Install requirements: `pip install -r requirements.txt`
4. Create a new Web App using **Manual Configuration** (Python 3.10)
5. Set Source Code and Working Directory to `/home/yourusername/smart-recipe-agent`
6. Set Virtualenv path to `/home/yourusername/.virtualenvs/myenv`
7. Edit the WSGI file to:
```python
import sys
path = '/home/yourusername/smart-recipe-agent'
if path not in sys.path:
    sys.path.insert(0, path)
from app import app as application
```
8. Add your `GEMINI_API_KEY` to a `.env` file in the project folder
9. Click **Reload** — your app is live

---

## Author

**Mariam Memon**
Kaggle 5-Day AI Agents Intensive: Vibe Coding Course with Google — Capstone 2026

---

*Built with Google Antigravity · Gemini API · Flask · PythonAnywhere*
