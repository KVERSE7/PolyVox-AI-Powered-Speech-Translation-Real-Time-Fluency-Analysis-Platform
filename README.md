# PolyVox – AI-Powered Speech Translation & Fluency Analysis

PolyVox is an AI-powered language processing platform that combines speech recognition, neural machine translation, pronunciation evaluation, and real-time fluency analysis. It helps users translate English speech into German, improve pronunciation, and monitor their speaking performance through intelligent audio analysis.

## ✨ Features

### 1. English-to-German Translation
- **Dual Input Support:** Accepts both text input and audio recordings through microphone or file upload.
- **Speech Recognition:** Uses OpenAI Whisper to convert spoken English into text.
- **Neural Machine Translation:** Employs a custom-trained Transformer model (`GerTran.keras`) for English-to-German translation.
- **IPA Transcription:** Generates phonetic representations of German translations using Epitran.
- **Text-to-Speech:** Converts German translations into audio using gTTS.

### 2. Pronunciation Evaluation
- **Speech Comparison:** Allows users to record their pronunciation of translated German sentences.
- **Pronunciation Metrics:** Evaluates speech using:
  - **Word Error Rate (WER):** Measures word-level transcription differences.
  - **Phone Error Rate (PER):** Measures phoneme-level differences.
  - **Pronunciation Score:** Provides an overall accuracy score.
- **Visual Comparison:** Displays target and recognized speech alongside their IPA transcriptions.

### 3. Real-Time Fluency Analysis
- **Live Speech Processing:** Analyzes spoken audio through a dedicated FastAPI server and WebSocket connection.
- **Speaking Rate:** Calculates Words Per Minute (WPM).
- **Filler Word Detection:** Identifies common fillers such as "um", "uh", and "like".
- **Fluency Scoring:** Generates a composite fluency score based on speech characteristics.
- **Pronunciation Feedback:** Highlights potentially mispronounced words using speech recognition confidence information.

## 🏗️ System Architecture

PolyVox consists of two main application components:

1. **Translation & Practice Interface:** A Streamlit application that handles text/audio input, translation, pronunciation assistance, and evaluation.
2. **Live Fluency Engine:** A FastAPI backend that processes live audio through WebSockets and provides real-time speech analysis through an HTML/JavaScript interface.

## 🛠️ Technology Stack

| Category | Technologies |
|---|---|
| Programming Language | Python |
| Frontend | Streamlit, HTML, CSS, JavaScript |
| Backend | FastAPI, WebSockets |
| Speech Recognition | OpenAI Whisper |
| Machine Translation | TensorFlow, Keras, Custom Transformer |
| Phonetic Processing | Epitran, IPA |
| Text-to-Speech | gTTS |
| Audio Processing | FFmpeg, Pydub |

## 📂 Project Structure

```text
PolyVox/
│
├── app.py                  # Main Streamlit application
├── live_server.py          # FastAPI real-time fluency server
├── run_suite.bat           # Launches both applications
├── model_utils.py          # Translation model utilities
├── GerTran.keras           # Pre-trained translation model
│
├── templates/
│   └── live.html           # Real-time fluency interface
│
├── ffmpeg_bin/             # Local FFmpeg binaries
│
├── requirements.txt        # Python dependencies
└── README.md               # Project documentation
```

## 🚀 Installation & Setup

### Prerequisites
- Python 3.8+
- FFmpeg
- Git

### 1. Clone the Repository

```bash
git clone <repository-url>
cd PolyVox
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Launch PolyVox

**Windows:**

```bash
run_suite.bat
```

Alternatively, start the applications separately:

**Terminal 1 – Live Fluency Server**

```bash
uvicorn live_server:app --host 127.0.0.1 --port 8000
```

**Terminal 2 – Main Application**

```bash
streamlit run app.py
```

### 4. Access the Applications

- **Main Translation Interface:** http://localhost:8501
- **Live Fluency Analysis:** http://localhost:8000

## 🧠 Key Concepts

- Automatic Speech Recognition (ASR)
- Transformer-based Neural Machine Translation
- Grapheme-to-Phoneme Conversion
- International Phonetic Alphabet (IPA)
- Word Error Rate (WER)
- Phone Error Rate (PER)
- Real-Time Audio Processing
- WebSocket Communication

## 🎯 Project Objective

PolyVox aims to combine language translation and speech intelligence into one platform, enabling users to move beyond basic text translation and actively improve their pronunciation and spoken fluency.

---

**PolyVox – Translate. Speak. Improve.**
