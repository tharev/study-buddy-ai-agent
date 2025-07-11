# study-buddy-ai-agent
# 🤖 Study Buddy AI Agent

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://python.org)
[![Flask](https://img.shields.io/badge/Flask-2.0%2B-green.svg)](https://flask.palletsprojects.com)
[![AI Powered](https://img.shields.io/badge/AI-Powered-orange.svg)](https://github.com/tharev/study-buddy-ai-agent)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> **An intelligent AI-powered study companion that provides personalized learning assistance, automated scheduling, quiz generation, and comprehensive academic performance analytics.**

## 🌟 Overview

The Study Buddy AI Agent is a comprehensive educational platform that leverages artificial intelligence to enhance the learning experience. It provides students with personalized study assistance, intelligent scheduling, automated quiz generation, collaborative study group coordination, and detailed performance analytics.

## ✨ Key Features

### 🧠 **AI-Powered Learning Assistant**
- **Personalized Recommendations**: ML-driven study path optimization
- **Adaptive Quiz Generation**: Dynamic difficulty adjustment based on performance
- **Knowledge Gap Analysis**: Identifies weak areas and suggests targeted learning
- **Study Pattern Optimization**: Analyzes effectiveness and suggests improvements

### 📅 **Smart Study Management**
- **Automated Scheduling**: AI-generated personalized study schedules
- **Progress Tracking**: Real-time monitoring of study sessions and effectiveness
- **Goal Setting & Achievement**: Customizable academic goals with progress visualization
- **Deadline Management**: Integration with assignment due dates and exam schedules

### 👥 **Collaborative Learning**
- **Study Group Coordination**: Smart matching and session planning
- **Real-time Collaboration**: Shared workspaces and synchronized study sessions
- **Peer Performance Comparison**: Anonymous benchmarking and motivation

### 📊 **Advanced Analytics**
- **Performance Dashboards**: Comprehensive visual analytics and insights
- **Trend Analysis**: Long-term progress tracking and prediction
- **Subject-wise Breakdown**: Detailed performance analysis by topic
- **Effectiveness Scoring**: AI-powered study session quality assessment

## 🚀 Quick Start

### Prerequisites
- Python 3.8 or higher
- pip package manager
- Virtual environment (recommended)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/tharev/study-buddy-ai-agent.git
   cd study-buddy-ai-agent
   ```

2. **Create and activate virtual environment**
   ```bash
   python -m venv study_buddy_env
   
   # On Windows
   study_buddy_env\Scripts\activate
   
   # On macOS/Linux
   source study_buddy_env/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Initialize NLP models** (first-time setup)
   ```bash
   python -c "import nltk; nltk.download('punkt'); nltk.download('stopwords'); nltk.download('wordnet')"
   python -m spacy download en_core_web_sm
   ```

5. **Run the application**
   ```bash
   python study_buddy_app.py
   ```

6. **Access the platform**
   - Open your browser to `http://localhost:5000`
   - Create an account or log in
   - Start your personalized learning journey!

## 📁 Project Structure

```
study-buddy-ai-agent/
├── study_buddy_app.py          # Main Flask application (700+ lines)
├── app.py                      # Alternative entry point
├── example_workflow.py         # Integration workflows and examples
├── requirements.txt            # 75+ Python dependencies
├── README.md                   # This comprehensive documentation
├── templates/                  # HTML templates (auto-generated)
├── static/                     # CSS, JS, and assets (auto-generated)
├── instance/                   # Database and config files (auto-generated)
└── migrations/                 # Database migrations (auto-generated)
```

## 🛠️ Core Components

### 1. **Main Application** (`study_buddy_app.py`)
- **Flask Web Framework**: Complete web application with 20+ routes
- **Database Models**: 8+ SQLAlchemy models for comprehensive data management
- **Authentication System**: Secure user registration and login
- **API Endpoints**: RESTful API for all functionality
- **AI Integration**: Machine learning models for personalized recommendations

### 2. **Workflow Integrations** (`example_workflow.py`)
- **Automated Study Scheduling**: AI-powered schedule generation
- **Quiz Generation & Assessment**: Adaptive testing with performance analysis
- **Study Group Coordination**: Smart group session planning
- **Canvas LMS Integration**: Sync with learning management systems
- **Performance Analytics**: Weekly reports with AI insights

### 3. **Dependencies** (`requirements.txt`)
- **Core Framework**: Flask, SQLAlchemy, Flask-Login
- **AI & ML**: scikit-learn, pandas, numpy, scipy
- **NLP**: nltk, spacy, textblob
- **Visualization**: matplotlib, seaborn, plotly
- **Authentication**: bcrypt, PyJWT, cryptography
- **Development**: pytest, black, flake8

## 🎯 Usage Examples

### Basic Study Session
```python
from study_buddy_app import StudyBuddyApp

app = StudyBuddyApp()

# Create a study session
session = app.create_study_session(
    user_id=1,
    subject="Mathematics",
    duration=60,  # minutes
    goals=["Complete Chapter 5", "Practice derivatives"]
)

# Get AI recommendations
recommendations = app.get_study_recommendations(user_id=1)
print(f"Suggested focus areas: {recommendations['focus_areas']}")
```

### Generate Personalized Quiz
```python
# Generate quiz based on user's performance
quiz = app.generate_adaptive_quiz(
    user_id=1,
    subject="Physics",
    difficulty="medium",
    question_count=10
)

# Analyze quiz results
results = app.analyze_quiz_results(quiz_id=quiz['id'])
print(f"Performance score: {results['score']}%")
```

### Workflow Integration
```python
from example_workflow import StudyBuddyWorkflow

workflow = StudyBuddyWorkflow()

# Automated study scheduling
schedule = workflow.create_study_schedule_workflow(
    user_id=123,
    subjects=["Math", "Physics", "Chemistry"],
    study_hours_per_day=4
)

# Canvas LMS sync
sync_results = workflow.canvas_lms_integration_workflow(user_id=123)
```

## 🔧 Configuration

### Environment Variables
Create a `.env` file in the root directory:

```env
SECRET_KEY=your-secret-key-here
DATABASE_URL=sqlite:///study_buddy.db
AI_API_KEY=your-openai-api-key
CANVAS_API_TOKEN=your-canvas-token
SLACK_WEBHOOK_URL=your-slack-webhook
```

### Database Setup
The application automatically creates the database on first run. For production:

```python
from study_buddy_app import app, db

with app.app_context():
    db.create_all()
    print("Database initialized successfully!")
```

## 🔌 Integrations

### Supported Platforms
- **Canvas LMS**: Assignment sync and grade tracking
- **Google Calendar**: Study session scheduling
- **Slack/Discord**: Progress notifications
- **Notion**: Note organization and knowledge management
- **Zoom**: Virtual study group coordination

### API Integrations
```python
# Example Canvas LMS integration
canvas_config = {
    "base_url": "https://your-school.instructure.com",
    "access_token": "your-canvas-token"
}

# Example notification setup
notifications = {
    "slack": "https://hooks.slack.com/services/YOUR/SLACK/WEBHOOK",
    "discord": "https://discord.com/api/webhooks/YOUR/DISCORD/WEBHOOK"
}
```

## 📊 Analytics & Reporting

### Performance Metrics
- Study session effectiveness scores
- Subject-wise progress tracking
- Learning velocity analysis
- Knowledge retention measurements
- Goal achievement rates

### Visualization Features
- Interactive progress dashboards
- Performance trend charts
- Subject comparison graphs
- Study pattern heatmaps
- Achievement milestone tracking

## 🧪 Testing

Run the test suite:
```bash
pytest tests/ -v
```

For specific test categories:
```bash
# Test AI functionality
pytest tests/test_ai_features.py

# Test web interface
pytest tests/test_routes.py

# Test database operations
pytest tests/test_models.py
```

## 🚀 Deployment

### Local Development
```bash
export FLASK_ENV=development
python study_buddy_app.py
```

### Production Deployment
```bash
# Using Gunicorn
gunicorn -w 4 -b 0.0.0.0:8000 study_buddy_app:app

# Using Docker
docker build -t study-buddy-ai .
docker run -p 8000:8000 study-buddy-ai
```

## 📈 Performance Optimization

### Database Optimization
- SQLite for development, PostgreSQL for production
- Database indexing for query optimization
- Connection pooling for concurrent users

### AI Model Efficiency
- Model caching for faster response times
- Batch processing for multiple users
- Asynchronous task processing with Celery

## 🤝 Contributing

We welcome contributions! Please see our contributing guidelines:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Setup
```bash
# Install development dependencies
pip install -r requirements-dev.txt

# Run code formatting
black study_buddy_app.py
flake8 study_buddy_app.py

# Run type checking
mypy study_buddy_app.py
```

## 📚 Documentation

### API Documentation
- **Authentication**: `/api/auth/` endpoints
- **Study Sessions**: `/api/sessions/` endpoints
- **Quiz Management**: `/api/quizzes/` endpoints
- **Analytics**: `/api/analytics/` endpoints
- **User Management**: `/api/users/` endpoints

### User Guides
- [Getting Started Guide](https://github.com/tharev/study-buddy-ai-agent/wiki/Getting-Started)
- [AI Features Guide](https://github.com/tharev/study-buddy-ai-agent/wiki/AI-Features)
- [Integration Setup](https://github.com/tharev/study-buddy-ai-agent/wiki/Integrations)
- [Troubleshooting](https://github.com/tharev/study-buddy-ai-agent/wiki/Troubleshooting)

## 🐛 Troubleshooting

### Common Issues

**Installation Problems**:
```bash
# If spaCy model fails to download
python -m spacy download en_core_web_sm --force-reinstall

# If NLTK data is missing
python -c "import nltk; nltk.download('all')"
```

**Database Issues**:
```bash
# Reset database
rm instance/study_buddy.db
python -c "from study_buddy_app import app, db; app.app_context().push(); db.create_all()"
```

**AI Model Issues**:
```bash
# Clear model cache
rm -rf ~/.cache/huggingface/transformers/
```

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **scikit-learn** for machine learning capabilities
- **Flask** for the web framework foundation
- **spaCy** for natural language processing
- **Plotly** for interactive visualizations
- **SQLAlchemy** for database management

## 📞 Support

- **Issues**: [GitHub Issues](https://github.com/tharev/study-buddy-ai-agent/issues)
- **Discussions**: [GitHub Discussions](https://github.com/tharev/study-buddy-ai-agent/discussions)
- **Wiki**: [Project Wiki](https://github.com/tharev/study-buddy-ai-agent/wiki)
- **Email**: study-buddy-ai@example.com

## 🔮 Roadmap

### Upcoming Features
- [ ] Mobile application (React Native)
- [ ] Advanced NLP for essay grading
- [ ] Integration with more LMS platforms
- [ ] Real-time collaborative whiteboards
- [ ] Voice-activated study assistant
- [ ] Gamification and achievement system
- [ ] Advanced AI tutoring capabilities
- [ ] Multi-language support

---

**⭐ Star this repository if you find it helpful!**

**🚀 Ready to enhance your learning experience? Get started now!**
