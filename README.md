LifeSaver AI: Autonomous Deadline Rescue Copilot
LifeSaver AI is a production-ready, full-stack AI productivity companion designed for the Google AI Hackathon.

Unlike traditional passive to-do lists that users easily ignore, LifeSaver AI actively intervenes to help students, professionals, and entrepreneurs complete tasks before deadlines are missed. Driven by Google Gemini, the platform prioritizes tasks, manages schedules, runs risk predictions, plans habits, and builds step-by-step emergency rescue routes.

🚀 Core Features
1. 🤖 Multi-Agent Gemini AI Engine
LifeSaver AI orchestrates 9 specialized Gemini API routes:

Task Analyzer: Parses natural language inputs to extract titles, descriptions, categories, and duration estimations.
Breakdown Agent: Decomposes high-level objectives into micro-subtasks.
Priority Engine: Computes importance scores based on schedule complexity and delay impact.
Smart Scheduler: Creates dynamic, hour-by-hour calendar flows mapping sleep, wake, and work windows.
Risk Predictor: Dynamically estimates completion risk categorizations (LOW, MEDIUM, HIGH) as deadlines approach.
Emergency Triage (Rescue Mode): Drops optional tasks, highlights absolute must-dos, and structures hyper-focused cramming windows.
Productivity Coach: Generates proactive mindset and workflow recommendations based on active workload.
Goal Planner: Breaks down long-term objectives into sequential milestones and suggested daily routines.
Subtask Assistant: Generates on-demand markdown guide blueprints and starter files for subtask steps.
2. 🎯 Goals & Habits Dashboard (/goals)
Daily Habits Board: A rolling 7-day routine tracker showing streaks. Completing a 7-day streak triggers canvas confetti.
AI Blueprint Planner: Autogenerates milestone checklists and target habits from high-level goals using Gemini.
3. 🎙️ Voice-Enabled Speech-to-Text (/tasks)
Microphone quick-add button leveraging native browser HTML5 Web Speech API to capture task specifications via speech transcription with zero API transcription cost.
4. ⚡ Autonomous Subtask Helper (/tasks/[id])
An interactive overlay simulating an autonomous terminal console. Triggers real-time agent output checks before generating outline drafts for micro-tasks.
5. 🚨 Emergency Rescue Workspace (/rescue)
High-contrast emergency UI displaying task countdowns, essential must-dos, and exported .ics calendar configurations to sync with Google Calendar or Apple Calendar.
🛠️ Technical Stack
Framework: Next.js (App Router, React 19)
Styling: Glassmorphism CSS UI, global Dark Mode.
Database & Auth (Dual Mode):
Supports live Firebase Auth & Firestore integrations.
Automatically falls back to LocalStorage with a mock user profile if environment keys are missing, making the demo fully operational.
Robust AI Fallbacks: Every API route features custom local fallback algorithms to guarantee zero service interruption during hackathon live presentations.
📦 Local Setup
Clone the repository and navigate to the project directory.
Install dependencies:
bash

npm install
Configure environment variables: Create a .env.local file at the root of the project:
env

GEMINI_API_KEY=your_gemini_api_key_here
Run the development server:
bash

npm run dev
Open http://localhost:3000 to view the application.
☁️ Production Deployment
The project is configured for serverless deployment on Google Cloud Run:

Build Container Configuration: Powered by Next.js standalone output configurations inside a multi-stage Dockerfile.
Exclusion Config (.gcloudignore): Ignores local configurations to prevent key leaks and secret scanning triggers.
GCP Deploy Command:
bash

gcloud run deploy lifesaver-ai \
  --source . \
  --region us-central1 \
  --allow-unauthenticated \
  --set-env-vars GEMINI_API_KEY="YOUR_KEY"
