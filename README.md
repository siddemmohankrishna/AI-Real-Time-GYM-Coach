# 🏋️ AI Real-Time GYM Coach

An AI-powered real-time gym coaching application that uses **computer vision, pose detection, exercise tracking, and AI voice feedback** to help users perform exercises with better form.

The application analyzes the user's body movements through a live camera, counts repetitions, tracks workout progress, detects form issues, and provides proactive AI coaching feedback.

---

## 🚀 Features

- 🎥 **Real-Time Pose Detection**
  - Detects body landmarks using MediaPipe Pose Landmarker.
  - Tracks the user's movements through the webcam.

- 🔢 **Automatic Rep Counting**
  - Counts exercise repetitions automatically.
  - Tracks completed sets and current-set repetitions.

- 🏋️ **Multiple Exercise Support**
  - Squats
  - Push-ups
  - Biceps Curls (Dumbbell)
  - Shoulder Press
  - Lunges

- 📐 **Exercise Form Analysis**
  - Calculates joint and body angles.
  - Detects common form issues.
  - Provides exercise-specific feedback.

- 🤖 **AI Coaching**
  - Uses an LLM-based coaching system to generate short and motivational feedback.
  - Provides contextual coaching based on workout events and detected form issues.

- 🔊 **AI Voice Feedback**
  - Converts coaching feedback into speech.
  - Provides real-time audio coaching during workouts.

- 📊 **Workout Tracking**
  - Tracks:
    - Total repetitions
    - Sets completed
    - Repetitions per set
    - Exercise type
    - Workout time

- 💾 **Workout History**
  - Stores workout information using SQLite.
  - Displays previous workout sessions inside the application.

- 🎨 **Custom UI**
  - Built with Streamlit.
  - Custom CSS styling and font support.
  - Dark-themed gym dashboard.

---

## 🧠 How It Works

The application follows this workflow:

```text
              ┌───────────────────┐
              │   Webcam Input    │
              └─────────┬─────────┘
                        │
                        ▼
              ┌───────────────────┐
              │ MediaPipe Pose    │
              │    Detection      │
              └─────────┬─────────┘
                        │
                        ▼
              ┌───────────────────┐
              │ Exercise Detector │
              └─────────┬─────────┘
                        │
             ┌──────────┴──────────┐
             ▼                     ▼
      Rep Counting            Form Analysis
             │                     │
             └──────────┬──────────┘
                        ▼
              ┌───────────────────┐
              │ Workout Tracking  │
              └─────────┬─────────┘
                        │
                        ▼
              ┌───────────────────┐
              │   AI LLM Coach    │
              └─────────┬─────────┘
                        │
                        ▼
              ┌───────────────────┐
              │ Text-to-Speech    │
              └─────────┬─────────┘
                        │
                        ▼
                🔊 Voice Feedback
| TechnologyPurpose |

## 🏋️ Supported Exercises

### 1. Squats

Tracks:

- Knee angle
- Back angle
- Squat depth
- Repetitions

**Example feedback:**

> "Lower your body a little more to reach proper squat depth."

### 2. Push-ups

Tracks:

- Elbow angle
- Body alignment
- Hip position
- Repetitions

### 3. Biceps Curls

Tracks:

- Elbow angle
- Shoulder stability
- Body swinging

### 4. Shoulder Press

Tracks:

- Elbow angle
- Arm extension
- Back arch

### 5. Lunges

Tracks:

- Front knee angle
- Torso angle
- Balance

---

## 🛠️ Technologies Used

| Technology | Purpose |
|------------|---------|
| **Python** | Core programming language |
| **Streamlit** | Web application interface |
| **MediaPipe** | Pose detection and landmark tracking |
| **OpenCV** | Image and video processing |
| **NumPy** | Numerical operations |
| **Streamlit-WebRTC** | Real-time webcam streaming |
| **Groq** | LLM-based AI coaching |
| **gTTS** | Text-to-speech feedback |
| **SQLite** | Workout data storage |
| **Pandas** | Workout history processing |
| **PyAV** | Video frame processing |

---
AI-Real-Time-GYM-Coach/
│
├── core/
│   ├── __init__.py
│   └── base_exercise.py
│
├── detectors/
│   ├── __init__.py
│   ├── squat.py
│   ├── pushup.py
│   ├── biceps_curl.py
│   ├── shoulder_press.py
│   └── lunges.py
│
├── services/
│   ├── __init__.py
│   │
│   ├── auth/
│   │   └── login_wall.py
│   │
│   ├── coaching/
│   │   ├── llm.py
│   │   ├── tts.py
│   │   └── voice_pipeline.py
│   │
│   ├── config/
│   │   └── workout_config.py
│   │
│   ├── persistence/
│   │   └── exercise_repository.py
│   │
│   ├── state/
│   │   └── session_defaults.py
│   │
│   ├── tracking/
│   │   └── metrics.py
│   │
│   ├── ui/
│   │   └── style_loader.py
│   │
│   └── vision/
│       ├── __init__.py
│       └── exercise_video_processor.py
│
├── ml_models/
│   └── pose_landmarker_full.task
│
├── static/
│   ├── style.css
│   └── AdobeClean.otf
│
├── main.py
├── requirements.txt
├── .gitignore
└── README.md

## ⚙️ Installation

### 1. Clone the Repository

Clone the project from GitHub:

```bash
git clone https://github.com/siddemmohankrishna/AI-Real-Time-GYM-Coach.git


### 2. create a Virtual Environment
Python 3.11 is recommended for this project.

```bash
python -m venv .venv

Activate the virtual environment.

```bash
.venv\Scripts\Activate.ps1(WINDOWS POWERSHELL)

### 3. Install Dependencies
Install the required Python Packages using pip:

```bash
pip install -r requirements.txt


### How it will look on GitHub

You'll get clean sections like:

**⚙️ Installation**  
→ Clone Repository  
→ Create Virtual Environment  
→ Install Dependencies  

**🔑 Configure Groq API**  
→ Environment variable  
→ Streamlit Secrets  

**▶️ Run the Application**  
→ Start Streamlit  
→ `http://localhost:8501`

This is the correct Markdown structure—**don't put extra triple backticks around the entire README section**, only around the individual commands/code blocks.

## 👨‍💻 Author

**Siddem Mohan Krishna**  
B.Sc. Data Science Student

Interested in **AI, Machine Learning, Data Science, Computer Vision, and Analytics**.

### 🔗 Connect With Me

- 💻 **GitHub:** [siddemmohankrishna](https://github.com/siddemmohankrishna)
- 💼 **LinkedIn:** [Siddem Mohan Krishna](https://www.linkedin.com/in/siddem-mohan-krishna-247984378/)
