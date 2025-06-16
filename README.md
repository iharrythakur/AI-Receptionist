# AI Salon Receptionist System

A human-in-the-loop AI receptionist system for a salon that handles customer calls, escalates to human supervisors when needed, and enhances its knowledge base over time.

## Features

- AI-powered call handling with natural conversation flow
- Professional salon-specific responses
- Appointment scheduling and management
- Service information and pricing inquiries
- Staff availability and expertise queries
- Human supervisor escalation system
- Real-time request tracking and management
- Knowledge base learning and updates

## Tech Stack

- **Backend**: Python/FastAPI
- **Frontend**: React
- **Voice Processing**: LiveKit
- **AI Components**:
  - **Deepgram**: Speech-to-Text (STT) - Converts user audio to text
  - **OpenAI**: Large Language Model (LLM) - Generates intelligent responses
  - **Cartesia**: Text-to-Speech (TTS) - Converts text responses to natural-sounding speech
- **Knowledge Base**: Cartesia
- **Database**: Firebase
- **Real-time Communication**: WebSocket

## Project Structure

```
salon-ai-receptionist/
├── backend/                 # FastAPI backend
│   ├── agent.py            # LiveKit voice agent implementation
│   └── requirements.txt    # Python dependencies
├── frontend/               # React frontend
├── config/                 # Configuration files
└── docs/                   # Documentation
```

## Setup Instructions

### Prerequisites

- Python 3.8+
- Node.js 16+
- Firebase account
- API Keys:
  - OpenAI API key
  - Deepgram API key
  - Cartesia API key
  - LiveKit credentials

### Installation

1. Clone the repository
2. Create and activate virtual environment:

   ```bash
   python -m venv .venv
   source .venv/bin/activate  # On macOS/Linux
   # or
   # .venv\Scripts\activate  # On Windows
   ```

3. Install backend dependencies:

   ```bash
   cd backend
   pip install -r requirements.txt
   ```

4. Install frontend dependencies:

   ```bash
   cd frontend
   npm install
   ```

5. Set up environment variables:
   ```bash
   cp .env.example .env
   # Edit .env with your credentials:
   # - LIVEKIT_URL
   # - LIVEKIT_API_KEY
   # - LIVEKIT_API_SECRET
   # - OPENAI_API_KEY
   # - DEEPGRAM_API_KEY
   ```

### Running the Application

1. Start the backend:

   ```bash
   cd backend
   uvicorn main:app --reload
   ```

2. Start the frontend:

   ```bash
   cd frontend
   npm start
   ```

3. Start the LiveKit agent:
   ```bash
   cd backend
   python agent.py
   ```

## System Architecture

The system consists of three main components:

1. **AI Receptionist Agent**

   - Handles incoming calls using LiveKit
   - Processes customer queries using OpenAI
   - Converts speech to text using Deepgram
   - Converts responses to speech using Cartesia
   - Escalates to human supervisors when needed
   - Updates knowledge base

2. **Supervisor Dashboard**

   - View and manage help requests
   - Respond to escalated queries
   - Monitor system performance
   - Update knowledge base

3. **Knowledge Base System**
   - Stores learned Q&A pairs
   - Provides context for AI responses
   - Updates based on supervisor feedback


#
