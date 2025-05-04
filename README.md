**AI Health Assistant (CrewAI + Ollama)**
This project is a local, privacy-focused AI-powered health assistant that analyzes personal fitness and wellness data (steps, sleep, weight, etc.) and provides personalized natural language feedback using a CrewAI agent and a local LLM via Ollama.

**Features**
CrewAI agent with goal, role, backstory, and tool integration

 Tools for health summary, nutrition guidance, and sleep coaching

 Uses preloaded user activity data (CSV)

 Maintains chat memory for contextual multi-turn conversations

 Runs completely offline with a local LLM (llama3, mistral, etc.)

**Files and Structure**
File	Description
health_chatbot_app.py	Main app logic (can be integrated with Streamlit or CLI)
tools.py	Contains tool logic (get_health_summary, suggest_nutrition, etc.)
agent.py	CrewAI agent definition and memory integration
data/weight_log_Info_merged.csv	Preloaded CSV with weight tracking
data/daily_activity_merged.csv	Preloaded CSV with daily steps, calories, etc.
README.md	Project overview and setup instructions

**CSV Data**
The project uses two datasets:

weight_log_Info_merged.csv: tracks user weight over time

daily_activity_merged.csv: tracks steps, calories burned, minutes active, etc.

These are merged in-memory using pandas for analysis by the tools.

**How It Works**
CSV data is preloaded using pandas

User enters a prompt (e.g., "How was my sleep last week?")

The CrewAI agent determines:

Which tools to invoke

What context to include from memory

The agent builds a prompt for the LLM (via Ollama)

The LLM returns a natural language response, which is shown to the user

**Requirements:**
pip install crewai pandas ollama langchain_community

**Notes**
No cloud API keys required

Fully local, memory-based interaction

Easily extendable: just add new tools!
