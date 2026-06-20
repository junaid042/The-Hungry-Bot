# The Hungry Bot


An AI-powered recipe agent that turns "what's in your kitchen" into a full meal plan — built as a capstone project for Google's 5-Day AI Agents Intensive: Vibe Coding Course, hosted by Kaggle.



# Live Demo

👉 MariamMemon.pythonanywhere.com

# Overview

Ever stared into your fridge with no idea what to cook? The Hungry Bot solves that. Tell it what ingredients you have on hand, and it acts as your personal kitchen assistant — finding real recipes, writing out the steps, and building your grocery list for anything you're missing.

# Features


🔍 Smart recipe search — uses Gemini with live web search grounding to find real, relevant recipes based on your ingredients
📝 Step-by-step instructions — clear, easy-to-follow cooking steps for every recipe
🛒 Auto-generated shopping list — instantly flags which ingredients you're missing
🔥 Calorie estimation — a rough per-serving calorie count for each recipe
🎯 Relevance scoring — evaluates how well each recipe actually matches your available ingredients
🎨 Clean, responsive UI — simple ingredient tags, one-click recipe generation


# Tech Stack

LayerTechnologyBackendPython (Flask)AI / ReasoningGoogle Gemini API (with Search grounding)FrontendHTML, CSS, JavaScriptDeploymentPythonAnywhereBuilt withGoogle Antigravity (agentic vibe coding)

# How It Works


User adds ingredients they currently have at home (e.g. potato, tomato, carrot, chicken)
The agent uses Gemini + Google Search grounding to find 2–3 real, relevant recipes
It generates clear step-by-step cooking instructions for each
It builds a "missing ingredients" shopping list automatically
It estimates calories per serving and scores recipe relevance


# Run It Locally

bashgit clone <this-repo-url>
cd the-hungry-bot
python -m venv venv
venv\Scripts\activate        # on Windows
pip install -r requirements.txt

Copy .env.template to .env and add your own Gemini API key (get one free at Google AI Studio):

GEMINI_API_KEY=your_actual_key_here

Then run:

bashpython app.py

Visit http://127.0.0.1:5000 in your browser.

# About This Project

This project was built from scratch with zero prior coding experience, as part of the 5-Day AI Agents Intensive: Vibe Coding Course with Google (hosted by Kaggle). It demonstrates core agentic concepts covered in the course — tool use (web search), evaluation (relevance scoring), security best practices (API key handling), and cloud deployment.

# Author
Mariam Memon
