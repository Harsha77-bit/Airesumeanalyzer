# 📄 AI Resume Analyzer

An intelligent resume analysis platform that uses AI/ML to evaluate resumes, extract skills, match job requirements, and provide actionable feedback for job seekers.

## 🌟 Features

- **Resume Analysis**: Extract text and analyze resumes using advanced ML algorithms
- **Skill Extraction**: Automatically identify and categorize technical and soft skills
- **Job Matching**: Match resume skills with job requirements and provide match percentages
- **ATS Optimization**: Check resume compatibility with Applicant Tracking Systems (ATS)
- **Resume Scoring**: Get an overall score and grade for your resume (A-F)
- **Contact Information**: Extract email, phone, LinkedIn, GitHub, and portfolio links
- **Experience Level Detection**: Estimate years of experience and seniority level
- **Suggestions**: Get personalized improvement recommendations
- **Secure Upload**: Encrypted file uploads with authentication
- **Dashboard**: View analysis history and resume scores

## 🏗️ Architecture

The project consists of three main components:

### 1. **Frontend** (React)
- Modern UI with React 19
- Real-time analysis feedback
- Authentication with JWT tokens
- Responsive design with CSS
- Interactive dashboard and upload interface

### 2. **Backend** (Node.js + Express)
- REST API with Express.js
- MongoDB database integration
- JWT-based authentication
- File upload with Multer
- Async resume analysis
- CORS-enabled for frontend communication

### 3. **ML Service** (Python + FastAPI)
- FastAPI server for ML models
- PDF text extraction
- Skill extraction and categorization
- Job matching algorithm
- ATS friendliness checker
- Score calculation and suggestions

## 📋 Prerequisites

- **Node.js** v16+ (for frontend & backend)
- **Python** 3.9+ (for ML service)
- **MongoDB** (local or Atlas)
- **npm** or **yarn**

## 🚀 Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/Jenish-Suvariya/Resume-Analyzer.git
cd Resume-Analyzer
```

### 2. Backend Setup
```bash
cd backend
npm install
```

Create `.env` file in `backend/` directory:
```env
PORT=5000
MONGO_URI=mongodb://localhost:27017/resume
JWT_SECRET=your_jwt_secret_key_here
ML_SERVICE_URL=http://localhost:8000
CLOUDINARY_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_SECRET_KEY=your_secret_key
```

Start backend:
```bash
npm start
```
Backend runs on: `http://localhost:5000`

### 3. ML Service Setup
```bash
cd ml-service
pip install -r requirements.txt
```

Start ML service:
```bash
python -m uvicorn app:app --host 0.0.0.0 --port 8000 --reload
```
ML Service runs on: `http://localhost:8000`

### 4. Frontend Setup
```bash
cd frontend
npm install
```

Create `.env` file in `frontend/` directory:
```env
REACT_APP_API_URL=http://localhost:5000/api
```

Start frontend:
```bash
npm start
```
Frontend runs on: `http://localhost:3000`

## 📁 Project Structure

```
Resume-Analyzer/
├── backend/                    # Node.js Express API
│   ├── config/
│   │   ├── db.js             # MongoDB connection
│   │   └── multer.js         # File upload config
│   ├── controllers/
│   │   ├── authController.js
│   │   └── resumeController.js
│   ├── middleware/
│   │   ├── authMiddleware.js
│   │   └── errorMiddleware.js
│   ├── models/
│   │   ├── Resume.js
│   │   └── User.js
│   ├── routes/
│   │   ├── authRoutes.js
│   │   └── resumeRoutes.js
│   ├── uploads/              # Resume uploads
│   ├── .env                  # Environment variables
│   ├── server.js             # Entry point
│   └── package.json
│
├── frontend/                   # React Application
│   ├── public/
│   ├── src/
│   │   ├── components/       # Reusable components
│   │   │   └── Navbar.js
│   │   ├── pages/            # Page components
│   │   │   ├── Home.js
│   │   │   ├── Login.js
│   │   │   ├── Register.js
│   │   │   ├── Upload.js
│   │   │   ├── Dashboard.js
│   │   │   └── Results.js
│   │   ├── context/
│   │   │   └── AuthContext.js
│   │   ├── services/
│   │   │   └── api.js        # API client
│   │   ├── App.js
│   │   ├── index.js
│   │   └── styles/
│   ├── .env                  # Environment variables
│   ├── package.json
│   └── README.md
│
├── ml-service/               # Python FastAPI ML Service
│   ├── app.py               # Main FastAPI app
│   ├── utils.py             # Analysis utilities
│   ├── skills_db.py         # Skills database
│   ├── requirements.txt      # Python dependencies
│   └── .gitignore
│
├── .gitignore
├── README.md
└── LICENSE
```

## 🔌 API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/me` - Get current user (requires auth)

### Resume Operations
- `POST /api/resume/upload` - Upload resume for analysis
- `GET /api/resume` - Get all user resumes
- `GET /api/resume/:id` - Get specific resume analysis
- `DELETE /api/resume/:id` - Delete resume

## 📊 Analysis Output

When a resume is analyzed, you receive:

```json
{
  "score": 85,
  "grade": "A",
  "scoreBreakdown": {
    "skills_depth": 90,
    "section_completeness": 85,
    "keyword_quality": 80,
    "content_length": 85,
    "contact_info": 100
  },
  "extractedSkills": ["JavaScript", "React", "Node.js", ...],
  "skillCount": 25,
  "categorizedSkills": {
    "frontend": ["React", "Vue"],
    "backend": ["Node.js", "Express"],
    "databases": ["MongoDB", "PostgreSQL"]
  },
  "detailedJobMatches": [
    {
      "title": "Full Stack Developer",
      "match_percent": 92,
      "readiness": "ready",
      "matched_required": ["JavaScript", "React"],
      "missing_required": ["Docker"]
    }
  ],
  "atsCheck": {
    "ats_friendly": true,
    "warnings": []
  },
  "suggestions": [
    {
      "priority": "high",
      "category": "Skills Gap",
      "message": "Add Docker to improve match with senior roles"
    }
  ]
}
```

## 🔐 Authentication

- User registration and login with JWT tokens
- Secure password hashing
- Token-based authentication for protected routes
- Automatic token refresh (optional)

## 🛡️ Security Features

- JWT authentication
- CORS enabled
- File upload validation
- Password hashing
- Input validation and sanitization
- Error handling middleware

## 📱 Responsive Design

- Mobile-friendly interface
- Works on desktop, tablet, and mobile devices
- Progressive enhancement

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 📧 Support

For issues, questions, or suggestions:
- Create an issue on GitHub
- Contact: your-email@example.com

## 🎯 Future Enhancements

- [ ] Video resume analysis
- [ ] LinkedIn profile integration
- [ ] Real-time collaboration
- [ ] Resume template builder
- [ ] Interview preparation module
- [ ] Career path recommendations
- [ ] Multi-language support
- [ ] Export analysis to PDF

## 👨‍💻 Author

**Jenish Suvariya**
- GitHub: [@Jenish-Suvariya](https://github.com/Jenish-Suvariya)
- Project: [Resume-Analyzer](https://github.com/Jenish-Suvariya/Resume-Analyzer)

---

**Happy Analyzing! 🚀**

Made with ❤️ for job seekers everywhere.
