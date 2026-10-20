🌍 AI Trip Planner
An agentic travel planning web application that leverages Large Language Models (LLMs) and advanced tool-calling to generate comprehensive, multi-day travel itineraries. Built with a FastAPI backend, a Streamlit frontend, and a robust LangGraph agent workflow, this application autonomously searches for attractions, calculates travel budgets, and designs tailored trips based on user preferences.

✨ Features
Agentic Workflow: Utilizes LangGraph to power an autonomous agent capable of deciding which tools to call (e.g., searching for attractions, calculating costs) based on the user's prompt.

Dual-Strategy Itineraries: Generates comparative travel plans (e.g., "Classic Highlights" vs. "Off-the-Beaten-Path") complete with daily schedules, hotel recommendations, and dining options.

Dynamic Expense Calculation: Features built-in Python tools to accurately calculate total hotel costs, total trip expenses, and daily budget breakdowns without relying on LLM arithmetic.

Real-Time Data Integration: Connects to Google Places and OpenWeather APIs to fetch accurate, real-world location and climate data.

Fast & Lightweight: Powered by Groq's high-speed inference (llama3-8b-8192) and standard OpenAI models, managed seamlessly via a custom configuration loader.

🛠️ Tech Stack
Backend: Python, FastAPI, Uvicorn

Frontend: Streamlit

AI & Orchestration: LangChain, LangGraph

LLM Providers: Groq, OpenAI

External APIs: Google Places API, OpenWeather API

Package Management: uv

🚀 Installation & Setup
1. Clone the repository

Bash
git clone https://github.com/rachitthakur067-hash/Ai_trip_planner.git
cd Ai_trip_planner
2. Create and activate a virtual environment
Using uv for fast package management:

Bash
uv venv
# On Windows:
.venv\Scripts\activate
# On macOS/Linux:
source .venv/bin/activate
3. Install dependencies

Bash
uv pip install -r requirements.txt
4. Configure Environment Variables
Create a .env file in the root directory of the project. Do not commit this file to version control.

Code snippet
# LLM Providers
OPENAI_API_KEY=your_openai_api_key_here
GROQ_API_KEY=your_groq_api_key_here

# External APIs
GOOGLE_API_KEY=your_google_cloud_api_key_here
GPLACES_API_KEY=your_google_cloud_api_key_here
OPENWEATHER_API_KEY=your_openweather_api_key_here
5. Configure the LLM
Ensure your config.yaml or config.json is set up to use your preferred model (e.g., llama3-8b-8192 for Groq).

💻 Usage
The application is split into a backend API and a frontend interface. You will need two terminal windows to run both simultaneously.

Terminal 1: Start the FastAPI Backend

Bash
python -m uvicorn main:app --host 0.0.0.0 --port 8000 --reload
The backend API will be available at http://localhost:8000. You can test endpoints directly via http://localhost:8000/docs.

Terminal 2: Start the Streamlit Frontend

Bash
streamlit run streamlit_app.py
This will open the interactive travel planner in your default web browser. Enter your destination, timeframe, and specific preferences (e.g., "Plan a 5-day trip to Barcelona for a football fan") to generate your custom itinerary
