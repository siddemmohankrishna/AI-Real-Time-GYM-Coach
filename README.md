# 🏋️ AI Real-Time GYM Coach

An **AI-powered real-time fitness coaching application** that uses **computer vision, pose detection, exercise tracking, and AI voice feedback** to help users perform exercises with better form.

The application analyzes body movements through a live webcam, automatically counts repetitions, tracks workout progress, detects exercise form issues, and provides proactive AI-powered coaching feedback.

---

## 🚀 Features

### 🎥 Real-Time Pose Detection

* Detects body landmarks using **MediaPipe Pose Landmarker**.
* Tracks body movements through the webcam.
* Processes exercise movements in real time.

### 🔢 Automatic Rep Counting

* Automatically counts exercise repetitions.
* Tracks repetitions for each set.
* Detects exercise movement phases to improve counting accuracy.

### 🏋️ Multiple Exercise Support

Currently supports:

* 🦵 Squats
* 💪 Push-ups
* 💪 Dumbbell Biceps Curls
* 🏋️ Shoulder Press
* 🦵 Lunges

### 📐 Exercise Form Analysis

* Calculates joint and body angles.
* Analyzes exercise-specific movement patterns.
* Detects common form issues.
* Provides corrective feedback to the user.

### 🤖 AI Coaching

* Uses an **LLM-based coaching system** to generate short and motivational feedback.
* Generates contextual feedback based on workout events.
* Provides coaching suggestions based on detected form issues.

### 🔊 AI Voice Feedback

* Converts AI-generated coaching messages into speech.
* Provides real-time audio feedback during workouts.
* Helps users receive coaching without constantly looking at the screen.

### 📊 Workout Tracking

Tracks important workout metrics including:

* Total repetitions
* Sets completed
* Repetitions per set
* Exercise type
* Workout duration
* Exercise performance

### 💾 Workout History

* Stores workout sessions using **SQLite**.
* Maintains previous workout information.
* Displays workout history directly inside the application.

### 🎨 Custom Gym Dashboard

* Built using **Streamlit**.
* Custom CSS styling.
* Custom font support.
* Dark-themed gym dashboard.
* Interactive workout interface.

---

# 🧠 How It Works

The application follows this workflow:

```text
┌────────────────────┐
│    Webcam Input    │
└─────────┬──────────┘
          │
          ▼
┌────────────────────┐
│  MediaPipe Pose    │
│     Detection      │
└─────────┬──────────┘
          │
          ▼
┌────────────────────┐
│  Exercise Detector │
└─────────┬──────────┘
          │
     ┌────┴─────┐
     ▼          ▼
┌───────────┐ ┌───────────────┐
│    Rep    │ │ Form Analysis │
│  Counting │ │               │
└─────┬─────┘ └───────┬───────┘
      │               │
      └───────┬───────┘
              ▼
┌────────────────────┐
│  Workout Tracking  │
└─────────┬──────────┘
          │
          ▼
┌────────────────────┐
│    AI LLM Coach    │
└─────────┬──────────┘
          │
          ▼
┌────────────────────┐
│   Text-to-Speech   │
└─────────┬──────────┘
          │
          ▼
       🔊 Voice
      Feedback
```

---

# 🏋️ Supported Exercises

## 1. Squats

Tracks:

* Knee angle
* Back angle
* Squat depth
* Repetitions

**Example AI feedback:**

> "Lower your body a little more to reach proper squat depth."

---

## 2. Push-ups

Tracks:

* Elbow angle
* Body alignment
* Hip position
* Repetitions

---

## 3. Biceps Curls

Tracks:

* Elbow angle
* Shoulder stability
* Body swinging
* Repetitions

---

## 4. Shoulder Press

Tracks:

* Elbow angle
* Arm extension
* Back arch
* Repetitions

---

## 5. Lunges

Tracks:

* Front knee angle
* Torso angle
* Balance
* Repetitions

---

# 🛠️ Technologies Used

| Technology           | Purpose                              |
| -------------------- | ------------------------------------ |
| **Python**           | Core programming language            |
| **Streamlit**        | Web application interface            |
| **MediaPipe**        | Pose detection and landmark tracking |
| **OpenCV**           | Image and video processing           |
| **NumPy**            | Numerical operations                 |
| **Streamlit-WebRTC** | Real-time webcam streaming           |
| **Groq**             | LLM-based AI coaching                |
| **gTTS**             | Text-to-speech feedback              |
| **SQLite**           | Workout data storage                 |
| **Pandas**           | Workout history processing           |
| **PyAV**             | Video frame processing               |

---

# 📁 Project Structure

```text
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
```

---

# ⚙️ Installation

## 1. Clone the Repository

```bash
git clone https://github.com/siddemmohankrishna/AI-Real-Time-GYM-Coach.git
cd AI-Real-Time-GYM-Coach
```

## 2. Create a Virtual Environment

Python **3.11** is recommended for this project.

```bash
python -m venv .venv
```

### Windows PowerShell

```powershell
.venv\Scripts\Activate.ps1
```

### macOS / Linux

```bash
source .venv/bin/activate
```

## 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

# 🔑 Configure Groq API

The AI coaching feature requires a **Groq API key**.

You can configure the API key using either of the following methods.

## Option 1 — Environment Variable

### Windows PowerShell

```powershell
$env:GROQ_API_KEY="your_api_key_here"
```

### macOS / Linux

```bash
export GROQ_API_KEY="your_api_key_here"
```

---

## Option 2 — Streamlit Secrets

Create a file:

```text
.streamlit/secrets.toml
```

Add:

```toml
GROQ_API_KEY = "your_api_key_here"
```

> ⚠️ Never commit your API key to GitHub.

---

# ▶️ Run the Application

Start the Streamlit application:

```bash
streamlit run main.py
```

Then open your browser and visit:

```text
http://localhost:8501
```

---

# 📊 Application Workflow

The complete workout pipeline works as follows:

```text
Webcam
   ↓
Pose Detection
   ↓
Body Landmark Extraction
   ↓
Exercise Detection
   ↓
┌─────────────────────┐
│                     │
▼                     ▼
Rep Counting     Form Analysis
│                     │
└──────────┬──────────┘
           ▼
    Workout Tracking
           ↓
      AI Coaching
           ↓
    Text-to-Speech
           ↓
    🔊 Voice Feedback
```

---

# 💡 Key Highlights

* ✅ Real-time computer vision
* ✅ AI-powered fitness coaching
* ✅ Real-time pose detection
* ✅ Automatic repetition counting
* ✅ Exercise-specific form analysis
* ✅ Multiple exercise support
* ✅ AI-generated corrective feedback
* ✅ Voice-based coaching
* ✅ Workout history tracking
* ✅ SQLite database integration
* ✅ Real-time webcam streaming
* ✅ Custom Streamlit dashboard

---

# 🔮 Future Improvements

Potential future enhancements include:

* 📱 Mobile application support
* 👥 Multi-user workout profiles
* 📈 Advanced workout analytics
* 🧠 Personalized workout recommendations
* 🏆 Gamification and achievement system
* 📊 Performance graphs and progress reports
* 🔥 Calorie estimation
* ❤️ Heart-rate integration
* 🎯 Personalized fitness goals
* ☁️ Cloud-based workout synchronization

---

# 👨‍💻 Author

## Siddem Mohan Krishna

**B.Sc. Data Science Student**

Interested in:

* Artificial Intelligence
* Machine Learning
* Data Science
* Computer Vision
* Analytics

### 🔗 Connect With Me

* 💻 **GitHub:** [siddemmohankrishna](https://github.com/siddemmohankrishna)
* 💼 **LinkedIn:** [Siddem Mohan Krishna](https://www.linkedin.com/in/siddem-mohan-krishna-247984378/)

---

# ⭐ Support

If you find this project useful, consider giving it a ⭐ on GitHub!

---

## 📜 License

This project is developed for educational and portfolio purposes.
