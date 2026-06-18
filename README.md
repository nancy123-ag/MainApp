Project Overview
EmoHeal is an AI-powered system that detects user emotions using multiple input methods such as facial expressions, voice, and interaction, and provides personalized therapy through music, chatbot, and games.
The system is designed to improve user mood by converting emotions into engaging and therapeutic responses.

Features
🎥 Face Emotion Detection (Camera Module)
🎤 Voice Emotion Analysis
💬 Chatbot Interaction
🎮 Mood-based Games (Fruit Ninja and Pacman)
🎵 Automatic Music Playback (Spotify)

🗄️ MongoDB Data Storage
1\. Camera Emotion Detection Module
AI-powered facial emotion recognition system that detects user mood in real-time and provides therapy through music playback.

📁 Project Structure
camera\_module/
│
├── main\_with\_spotify.py     # Core AI logic (camera + emotion + Spotify)
├── backend\_launcher.py      # Flask backend to start/stop module
├── app.js                   # Frontend JS (API calls)
├── index.html               # User interface (Start/Stop buttons)
│
├── .cache                   # Cache file (ignore)

⚙️ Environment Setup
Install Dependencies:
pip install opencv-python fer spotipy pymongo flask

🔄 Working Flow
Camera Input
&#x20;   ↓
Face Detection (OpenCV)
&#x20;   ↓
Emotion Detection (FER - CNN)
&#x20;   ↓
Emotion Mapping
&#x20;   ↓
Spotify API (Play Song)
&#x20;   ↓
Store in MongoDB

🧠 Emotion Detection Pipeline
Face Image
&#x20;   ↓
FER Library (CNN Model)
&#x20;   ↓
Emotion Probabilities
&#x20;   ↓
Dominant Emotion Selection
🎵 Music Playback Pipeline
Detected Emotion
&#x20;   ↓
Emotion → Query Mapping
&#x20;   ↓
Spotify API (Spotipy)
&#x20;   ↓
Play Song on Active Device

🎯 Emotion Output
The module detects:
Happy
Sad
Angry
Fear
Surprise
Neutral
Disgust

🔌 API Endpoints
Method	Endpoint	Description
GET	/start	Start camera + emotion detection
GET	/stop	Stop system

📊 Database Integration
Database: MongoDB
Collection: face\_music\_history
Stores:
Emotion
Song
Timestamp

2\. EmoHeal — Voice Emotion Detection Module
AI-powered emotional analysis module that detects user mood from voice input and supports therapeutic responses.

📁 Project Structure
voice\_module/
│
├── app.py                        # Flask backend (main server)
├── mood\_spotify\_player\_debug.py  # Core logic (voice + emotion + Spotify)
├── script.js                     # Frontend interaction (API calls)
├── test\_app.py                   # Testing script
│
├── templates/
│   └── index.html               # UI interface
│
├── audio/
│   ├── voice.wav                # Recorded voice input
│   └── temp\_voice.wav           # Temporary audio file
│
├── .vscode/
│   └── settings.json            # VS Code config
│
├── venv/                        # Virtual environment (ignore in submission)
├── \_\_pycache\_\_/                 # Python cache (auto-generated)
├── .cache                       # System cache

⚙️ Environment Setup

Install Dependencies
pip install speechrecognition pyaudio librosa numpy

🔄 Working Flow
Voice Input
&#x20;   ↓
Audio Capture (Microphone)
&#x20;   ↓
Feature Extraction (Pitch, Tone)
&#x20;   ↓
Emotion Detection Model
&#x20;   ↓
Output Emotion

🔌 Input Pipeline
User Voice
&#x20;   ↓
Microphone Capture
&#x20;   ↓
Audio Preprocessing (Noise Removal)
&#x20;   ↓
Feature Extraction

🧠 AI Pipeline
Audio Features
&#x20;   ↓
Emotion Detection Model
&#x20;   ↓
Emotion Classification
&#x20;   ↓
Send to System

🎯 Emotion Detection
The module detects emotions such as:
Happy
Sad
Angry
Neutral

3\. Chatbot Interaction

\# EmoHeal — Psychiatric Chatbot
AI-powered emotional support chatbot with crisis detection, mood tracking, and therapeutic responses.

&#x20;Quick Start
&#x20;One click (Windows)
Double-click start-all.bat
&#x20;📁 Project Structure

emoheal/
├── backend/
│   ├── main.py
│   ├── run.py
│   ├── .env                    ← never commit this
│   └── app/
│       ├── config.py
│       ├── database/
│       │   └── db.py
│       ├── models/
│       │   └── schemas.py
│       ├── routes/
│       │   ├── auth.py
│       │   ├── chat.py
│       │   └── history.py
│       └── services/
│           ├── auth\_service.py
│           ├── topic\_guard.py
│           ├── crisis\_detector.py
│           └── ai\_therapist.py
│
└── frontend/

&#x20;   ├── index.html
&#x20;   ├── vite.config.js
&#x20;   ├── tailwind.config.js
&#x20;   └── src/
&#x20;       ├── main.jsx
&#x20;       ├── index.css
&#x20;       ├── App.jsx
&#x20;       ├── api/
&#x20;       │   └── client.js
&#x20;       ├── context/
&#x20;       │   └── AuthContext.jsx
&#x20;       ├── pages/
&#x20;       │   ├── Login.jsx
&#x20;       │   ├── Register.jsx
&#x20;       │   ├── Chat.jsx
&#x20;       │   └── History.jsx
&#x20;       └── components/
&#x20;           ├── Navbar.jsx
&#x20;           ├── ChatBubble.jsx
&#x20;           └── CrisisAlert.jsx

⚙️ Environment Setup
Create `backend/.env`:
MONGODB\_URL=mongodb+srv://emoheal\_team:password@cluster.mongodb.net/
DB\_NAME=emoheal

📦 Install Dependencies
Backend:
```powershell
cd backend
python -m venv venv
venv\\Scripts\\activate
pip install -r requirements.txt

Frontend:
```powershell
cd frontend
npm install

```
🔌 API Endpoints
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/register` | Register new user |
| POST | `/api/auth/login` | Login |
| GET | `/api/auth/me` | Get current user |
| WS | `/ws/chat/{user\_id}?token=<jwt>` | Real-time chat |
| GET | `/api/history/sessions` | All chat sessions |
| GET | `/api/history/messages/{session\_id}` | Session messages |
| GET | `/api/history/mood-summary` | Mood trends |
| GET | `/api/history/latest-mood` | Latest mood |
| GET | `/api/history/crisis-alerts` | Crisis alerts |

🤖 AI Pipeline
User Message
        ↓  
Topic Guard      → off-topic? redirect politely
         ↓
Crisis Detector  → high? show crisis alert + helplines
          ↓
AI Therapist     → generate warm therapeutic response
         ↓
Save to MongoDB + Send to user

🆘 Crisis Helplines (India)
\- iCall:9152987821
\- Vandrevala Foundation: 1860-2662-345
\- Emergency: 112

4\. Mood-based Games (Fruit Ninja and Pacman)
**This module includes mood-based interactive games such as Fruit Ninja and Pacman to improve user engagement and reduce stress.**

**📁 Project Structure**
**games\_module/**

**│**
**├── fruit\_ninja/**
**│   ├── main.py                 # Main game logic**
**│   ├── back.jpg                # Background image**
**│   ├── background.mp3          # Background music**
**│   ├── bomb.mp3                # Bomb sound**
**│   ├── cut.mp3                 # Slice sound**
**│   ├── comic.ttf               # Game font**
**│   │**
**│   └── images/**
**│       ├── background.jpg**
**│       ├── bomb.png**
**│       ├── explosion.png**
**│       ├── game\_over.png**
**│       ├── guava.png**
**│       ├── melon.png**
**│       ├── orange.png**
**│       ├── pomegranate.png**
**│       ├── half\_guava.png**
**│       ├── half\_melon.png**
**│       ├── half\_orange.png**
**│       ├── half\_pomegranate.png**
**│       ├── red\_lives.png**
**│       └── white\_lives.png**
**│**
**├── pacman/**
**│   └── pacman.py              # Pacman game logic**
**│**
**└── README.md                  # Games module documentation**

**🎮 Games Included**
**1. Fruit Ninja Game**
**-Slice fruits using mouse**
**-Avoid bombs**
**-Score increases with successful cuts**
**-Includes sound effects and animations**

**2. Pacman Game**
**-Classic maze-based game**
**-Player collects points**
**-Avoid enemies**
**-Improves focus and engagement**
**⚙️ Dependencies**
**pip install pygame**

**▶️ How to Run**
**Run Fruit Ninja**
**python main.py**
**Run Pacman**
**python pacman.py**

**🎯 Purpose**
**Improve user mood**
**Provide stress relief**
**Enhance engagement**
**5.** Automatic Music Playback (Spotify)
The system integrates the Spotify Web API to automatically play music based on detected user emotions in real time.

⚙️ How It Works
Emotion is detected using camera or voice module
Emotion is mapped to a music category
Spotify API is used to search relevant songs
A random track is selected
Music is played on the user's active Spotify device

🧠 Implementation Details
Integrated using Spotipy (Spotify Python API wrapper)
Key API functionalities used:
Search songs → sp.search()
Get devices → sp.devices()
Play music → sp.start\_playback()
Pause playback → sp.pause\_playback()

&#x20;🎯 Emotion → Music Mapping
| Emotion | Music Type          |
|--------|----------------------|
| Happy  | Party / Happy Songs  |
| Sad    | Emotional Songs      |
| Angry  | Motivational Songs   |
| Neutral| Relaxing Music       |

📌 Requirements
Spotify Premium account (used in this project)
Active Spotify device (mobile/desktop)
Internet connection

6.MongoDB Data Storage
The system uses MongoDB Atlas (cloud database) to store user emotion and music history for tracking and analysis.

⚙️ How It Works
Emotion is detected from camera/voice
Song is played based on emotion
Data is stored in MongoDB Atlas
Records can be used for history and analytics

🧠 Implementation Details
Connected using MongoDB connection string
Used pymongo library for database operations
Data is stored in real-time
📊 Database Structure
Database Name: EmoHeal
Collection: face\_music\_history 

🧾 Document Structure
Each record in the database follows this format:
{
&#x20; "mood": "happy",
&#x20; "song": "Kesariya - Arijit Singh",
&#x20; "timestamp": "2026-04-08T12:30:00"
}

📌 Features
Cloud-based storage (MongoDB Atlas)
Real-time data saving
Mood tracking support
Scalable and secure

Future Scope
🤖 Improve emotion detection using advanced AI models
📱 Develop a mobile application for real-time usage
🎧 Provide personalized music recommendations based on user history
☁️ Deploy the system on cloud for scalability and remote access
📊 Add analytics dashboard for mood tracking and insights

⭐ Conclusion
EmoHeal is a multi-modal AI system that integrates computer vision, voice processing, APIs, and interactive modules to provide a complete emotion-driven therapy experience.



