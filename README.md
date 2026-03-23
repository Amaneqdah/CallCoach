# Call Coach — Real-Time AI Coaching for Customer Service Calls

Call Coach is an AI-powered training platform for customer-service agents. It supports voice-based practice sessions by transcribing calls in real time, analyzing conversation context, and providing actionable coaching during training. After each session, the system generates a post-call evaluation report to help agents improve their communication and service quality.

This project was designed to make customer-service training more scalable, consistent, and effective through real-time AI assistance.

---

## Problem

Training customer-service agents is often time-consuming, expensive, and inconsistent. Managers cannot monitor every call in real time, and new agents may struggle to receive immediate, actionable feedback while practicing.

## Solution

Call Coach provides:
- real-time AI guidance during training calls
- structured post-call evaluation
- a more consistent and scalable training experience
- support for both trainees and employers

---

## Key Features

- Live voice-call support using WebRTC
- Real-time speech transcription
- AI-generated coaching during training sessions
- Context-aware suggestions based on conversation flow
- Post-call evaluation and feedback report
- Role-based experience for trainees and employers
- Exam mode for performance assessment without live coaching
- FastAPI backend with WebSocket support

---

## System Architecture

```text
Browser (Microphone + WebRTC)
        ↓
FastAPI Backend
        ↓
AssemblyAI (Live Transcription)
        ↓
LLM (Coaching + Evaluation)
        ↓
Real-Time Guidance + Final Report
Workflow
The user starts a voice-based training session.
Audio is streamed and transcribed in real time.
The AI analyzes the conversation context and checks for service quality signals.
During training mode, the system provides live coaching tips.
After the session ends, the system generates a final evaluation report.
Tech Stack
Python 3.11
FastAPI
Uvicorn
WebSockets
WebRTC
AssemblyAI
OpenAI / Mistral
Jinja2
Railway
Project Highlights
Built a real-time AI-assisted training workflow
Integrated live transcription with LLM-based reasoning
Designed coaching logic that avoids repetitive or disruptive feedback
Supported both real-time guidance and post-call evaluation
Developed a prototype suitable for intelligent training environments
Requirements

Install dependencies from requirements.txt:

fastapi
uvicorn[standard]
python-dotenv
assemblyai
mistralai
jinja2
pydantic
websockets
itsdangerous
Local Setup
1. Clone the repository
git clone https://github.com/AmaneQaddah/call-coach.git
cd call-coach
2. Create a virtual environment
python -m venv venv

Activate it:

Windows

venv\Scripts\activate

macOS / Linux

source venv/bin/activate
3. Install dependencies
pip install -r requirements.txt
4. Create a .env file
OPENAI_API_KEY=your_openai_key
ASSEMBLYAI_API_KEY=your_assemblyai_key

Do not commit this file to GitHub.

5. Run the application
uvicorn app:app --reload

Open in the browser:

http://127.0.0.1:8000
http://127.0.0.1:8000/docs
Deployment

This project requires a persistent backend server because it relies on WebSockets and live audio processing.

Railway start command
uvicorn app:app --host 0.0.0.0 --port $PORT
Required environment variables
OPENAI_API_KEY
ASSEMBLYAI_API_KEY
Environment Variables
Variable	Description
OPENAI_API_KEY	Used for AI coaching and post-call evaluation
ASSEMBLYAI_API_KEY	Used for live speech transcription

Example usage in Python:

import os

openai_key = os.getenv("OPENAI_API_KEY")
assemblyai_key = os.getenv("ASSEMBLYAI_API_KEY")
AI Logic

The system combines real-time speech transcription with LLM-based reasoning to:

monitor the flow of the conversation
detect whether important service behaviors are being followed
provide context-aware coaching during training
avoid repeating the same advice unnecessarily
generate a final performance summary after the call
Known Limitations
Free-tier deployment may cause cold starts
Browser microphone permissions are required
Real-time performance depends on network quality
This is currently a prototype-scale system
Future Improvements
Employer performance dashboard
Persistent analytics and call history
Multilingual support
More advanced coaching personalization
Multi-scenario and multi-agent simulation
Screenshots

Add screenshots here if available:

![Training Screen](assets/training-screen.png)
![Evaluation Report](assets/evaluation-report.png)
Project Context

This project was developed as part of an academic project focused on AI-assisted training, real-time feedback, and human-centered system design.

Author

Amani Qaddah
GitHub: https://github.com/AmaneQaddah
