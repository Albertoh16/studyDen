# Study Buddy (StudyDen)

**Turn studying into an interactive and rewarding adventure!**

Study Buddy is a mobile application that gamifies the learning experience by combining personalized avatar companions, AI-generated educational content, and engaging mini-games. Scan your physical textbooks, let AI generate quiz questions, and watch your Study Buddy avatar level up as you learn!

---

## Demo

<div align="center">

[![Watch the demo](./videoDemoPNG.png)](./StudyDenDemo.mp4)

</div>

---

## Features

### Create and Customize Avatars
- **Personalized Companion**: Create a unique Study Buddy avatar with custom names
- **Choose Your Species**: Select from adorable animal companions
- **Level Progression**: Level up your avatar with experience points (XP) earned through studying
- **Character Growth**: Watch your companion evolve as you progress through your studies

### Scan and Store Books
- **Camera Integration**: Take pictures of multiple pages from physical textbooks using your phone
- **Digital Library**: Save and organize digital versions of your books directly in the app
- **Book Management**: Name, categorize, and track all your study materials
- **Persistent Storage**: All book data stored securely on your device

### lay Mini-Games
- **Interactive Learning**: Engage with quiz-based mini-games generated from your book content
- **Multiple Choice Questions**: Answer questions based on scanned material
- **Instant Feedback**: Know immediately if your answer is correct or incorrect
- **XP Rewards**: Earn experience points for correct answers to level up your avatar

### AI-Generated Questions
- **OpenAI Integration**: Questions and answers generated using ChatGPT API
- **OCR Text Extraction**: Tesseract OCR extracts text from scanned book pages
- **Intelligent Processing**: AI analyzes content and creates relevant study questions
- **Adaptive Content**: Questions tailored to the specific material you're studying

### Local Data Storage
- **SQLite Database**: All data stored securely on your device
- **User Profiles**: Avatar details including name, species, level, and XP
- **Book Repository**: Complete storage of book names, pages, and questions
- **Offline Access**: Study anytime without internet connection (after initial question generation)

### Unity-Powered UI
- **Rich Graphics**: Beautiful, responsive interface built with Unity Game Engine
- **Smooth Animations**: Fluid character movements and transitions
- **Cross-Platform**: Consistent experience on both Android and iOS
- **Intuitive Design**: User-friendly interface optimized for mobile devices

---

## Tech Stack

### Frontend
- **Unity Game Engine**: C# for rich mobile game development
- **Platform**: Android and iOS support
- **UI Framework**: Unity UI system with custom components

### Backend
- **Framework**: FastAPI (Python)
- **Database**: SQLite with SQLModel ORM
- **Authentication**: Passlib with bcrypt hashing
- **API Documentation**: Auto-generated with OpenAPI/Swagger

### AI & Image Processing
- **OCR Engine**: Tesseract (pytesseract Python wrapper)
- **AI Integration**: OpenAI ChatGPT API (GPT-4o-mini model)
- **Image Processing**: OpenCV for image manipulation
- **Text Extraction**: PIL (Python Imaging Library)

### Data Management
- **ORM**: SQLModel for database operations
- **Validation**: Pydantic for data validation and schemas
- **Environment**: Python-dotenv for configuration management

### Deployment
- **Containerization**: Docker support included
- **CORS**: Cross-Origin Resource Sharing enabled
- **REST API**: RESTful architecture with proper HTTP methods

---

## Getting Started

### Prerequisites

**Backend Requirements:**
- Python 3.8 or higher
- pip (Python package installer)
- OpenAI API key
- Tesseract OCR installed on system

**Frontend Requirements:**
- Unity 2020.3 LTS or higher (for development)
- Android Studio (for Android builds)
- Xcode (for iOS builds, macOS only)

### Backend Setup

1. **Navigate to backend directory**:
```bash
cd studyDen/backend
```

2. **Create virtual environment**:
```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Linux/macOS:
source venv/bin/activate
# On Windows:
venv\Scripts\activate
```

3. **Install dependencies**:
```bash
pip install -r requirement.txt
```

4. **Install Tesseract OCR**:
   - **Windows**: Download from [GitHub](https://github.com/UB-Mannheim/tesseract/wiki)
   - **macOS**: `brew install tesseract`
   - **Linux**: `sudo apt-get install tesseract-ocr`

5. **Configure environment variables**:

Create a `.env` file in the `/backend` directory:
```env
OPENAI_API_KEY=your_openai_api_key_here
```

6. **Run the backend server**:
```bash
# Development mode (accessible from local network devices)
uvicorn main:app --reload --host 0.0.0.0 --port 8000

# Or using FastAPI CLI
fastapi dev --host 0.0.0.0
```

7. **Access the API**:
   - **API Docs**: http://localhost:8000/docs
   - **Alternative Docs**: http://localhost:8000/redoc
   - **Health Check**: http://localhost:8000/

### Docker Deployment (Optional)

```bash
# Build the Docker image
docker build -t studyden-backend ./backend

# Run the container
docker run -p 8000:8000 -e OPENAI_API_KEY=your_key_here studyden-backend
```

## Security Features

- **Password Hashing**: Bcrypt algorithm with salt
- **CORS Protection**: Configurable cross-origin policies
- **SQL Injection Prevention**: SQLModel ORM parameterized queries
- **API Key Security**: Environment variable management for OpenAI key
- **Input Validation**: Pydantic schemas validate all inputs

---

## Key Technologies

### Tesseract OCR
Open-source optical character recognition engine that converts images of text into machine-readable text. Supports 100+ languages and can handle various image qualities.

### OpenAI ChatGPT API
GPT-4o-mini model used for intelligent question generation. Analyzes extracted text and creates relevant, educational multiple-choice questions with appropriate difficulty levels.

### FastAPI
Modern, high-performance Python web framework with automatic API documentation, async support, and built-in data validation using Pydantic.

### SQLModel
Combines SQLAlchemy ORM with Pydantic validation, providing type-safe database operations with automatic schema validation.

### Unity Game Engine
Cross-platform game engine enabling rich graphics, smooth animations, and consistent mobile experience across iOS and Android.
