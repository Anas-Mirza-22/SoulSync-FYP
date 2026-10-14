# Soul-Sync

Soul-Sync is an AI-powered mental wellness assistant that helps users reflect on their emotions, receive supportive guidance, and access crisis resources when needed.

The project combines conversational AI, emotion detection, crisis awareness, and preference-based support to create a compassionate digital wellness experience. It is designed to offer empathetic responses in either Islamic or psychological styles, depending on the user's preference.

> This project is intended for emotional support and wellness assistance. It is not a substitute for professional mental health care or emergency intervention.

---

## Overview

Soul-Sync is built to:
- detect emotional intent from user messages
- generate context-aware and empathetic responses
- recognize crisis-related language and provide immediate safety guidance
- support both Islamic and psychological counseling approaches
- store analytics for admin monitoring and system improvement

---

## Features

### User experience
- AI-driven emotional chat experience
- conversation memory across multiple turns
- user preference selection for Islamic, psychological, or hybrid guidance
- crisis detection and emergency support resources
- responsive landing page and chat interface
- explainable emotion cues using SHAP-style token importance

### Admin features
- secure admin login flow
- analytics dashboard for usage and safety trends
- emotion distribution tracking
- crisis severity summaries
- hourly and daily activity monitoring
- recent crisis event reporting

---

## Tech Stack

### Backend
- Python
- Flask
- PyTorch
- Hugging Face Transformers
- SHAP
- SQLite
- Requests
- python-dotenv

### Frontend
- React
- Vite
- JavaScript
- Recharts
- React Markdown

---

## Project Structure

```text
SOULSYNC/
├── README.md
├── soulsync-backend/
│   ├── app.py
│   ├── responses.json
│   ├── requirements.txt
│   ├── analytics.db
│   └── .env
└── soulsync-frontend/
    ├── package.json
    ├── vite.config.js
    ├── src/
    └── public/
```

---

## How It Works

### Backend flow
1. Receives a message from the frontend.
2. Runs emotion detection on the text.
3. Checks for crisis patterns such as self-harm or suicidal language.
4. Selects an appropriate response:
   - crisis response for urgent situations
   - Claude-based contextual response for general chat
   - fallback response from the JSON library if needed
5. Logs analytics to SQLite.
6. Returns the emotion, confidence, crisis result, and assistant response.

### Frontend flow
- starts or resumes a chat session
- sends messages to the backend
- renders AI responses in the chat UI
- shows emergency and crisis guidance if needed
- allows admin access to analytics

---

## API Endpoints

The backend exposes the following key routes under `/api`:

- `GET /api/health` — checks backend health
- `GET /api/info` — returns app metadata and supported emotions
- `POST /api/session/start` — creates a new session
- `POST /api/chat` — sends a message and receives a response
- `POST /api/emotion/detect` — detects emotion for a single message
- `GET /api/crisis/resources` — returns local crisis resources
- `POST /api/admin/login` — logs in an admin user
- `GET /api/admin/verify` — verifies the admin token
- `GET /api/admin/analytics` — returns analytics data for the dashboard

---

## Environment Variables

Create a `.env` file in the backend directory:

```env
ADMIN_PASSWORD=your_secure_admin_password
CLAUDE_KEY=your_claude_api_key
WEB3FORMS_KEY=your_web3forms_access_key
COUNSELOR_EMAIL=your_support_email@example.com
```

---

## Local Setup

### Backend
```bash
cd soulsync-backend
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python app.py
```

The backend runs at:
```text
http://localhost:5000
```

### Frontend
```bash
cd soulsync-frontend
npm install
npm run dev
```

The frontend runs at:
```text
http://localhost:5173
```

---

## Safety Note

This app includes crisis-detection logic and emergency guidance for users in distress. However, it is not a medical professional and should not be treated as a substitute for licensed therapy, emergency assistance, or human support in critical situations.

If a user is in immediate danger, contact emergency services right away.

---

## License

This project does not currently include a license file. If you plan to publish or distribute it publicly, add a license before sharing.

---

## Summary

Soul-Sync is a thoughtful AI wellness project designed to support emotional wellbeing through compassionate, context-aware conversations. It blends modern AI with crisis-aware safety design and a culturally aware support model, making it a strong foundation for a mental wellness product MVP.

## License

This project does not currently include a defined license file. If you are publishing or sharing it publicly, add a license before distribution.

---

## Summary

Soul-Sync is a compelling mental wellness chatbot prototype that combines conversational AI, emotional analysis, crisis support, and analytics in one connected app. It is useful as a concept demo and strong MVP foundation, and it is especially promising for users wanting supportive, context-aware conversations with a culturally aware perspective.
