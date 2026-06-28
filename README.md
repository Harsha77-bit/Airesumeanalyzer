 AI Resume Analyzer :-
An intelligent resume analysis platform that uses AI/ML to evaluate resumes, extract skills, match job requirements, and provide actionable feedback for job seekers.

-----------------*Features*-----------------------------------------------------


Resume Analysis: Extract text and analyze resumes using advanced ML algorithms
Skill Extraction: Automatically identify and categorize technical and soft skills
Job Matching: Match resume skills with job requirements and provide match percentages
ATS Optimization: Check resume compatibility with Applicant Tracking Systems (ATS)
Resume Scoring: Get an overall score and grade for your resume (A-F)
Contact Information: Extract email, phone, LinkedIn, GitHub, and portfolio links
Experience Level Detection: Estimate years of experience and seniority level
Suggestions: Get personalized improvement recommendations
Secure Upload: Encrypted file uploads with authentication
Dashboard: View analysis history and resume scores


------------------*Architecture* ---------------------------------


The project consists of three main components:

1. Frontend (React)
Modern UI with React 19
Real-time analysis feedback
Authentication with JWT tokens
Responsive design with CSS
Interactive dashboard and upload interface
2. Backend (Node.js + Express)
REST API with Express.js
MongoDB database integration
JWT-based authentication
File upload with Multer
Async resume analysis
CORS-enabled for frontend communication
3. ML Service (Python + FastAPI)
FastAPI server for ML models
PDF text extraction
Skill extraction and categorization
Job matching algorithm
ATS friendliness checker
Score calculation and suggestions




*****Before u start to run the project please cete a .env flle in th backend and fronend.




Start backend:

npm start





3. ML Service Setup
cd ml-service
pip install -r requirements.txt
Start ML service:
python -m uvicorn app:app --host 0.0.0.0 --port 8000 --reload(give ur choice port number)
ML Service runs on: http://localhost:8000





4. Frontend Setup
cd frontend
npm install
Start frontend:
npm start







 -------------*API Endpoints*----------------------------


 
Authentication
POST /api/auth/register - Register new user
POST /api/auth/login - Login user
GET /api/auth/me - Get current user (requires auth)
Resume Operations
POST /api/resume/upload - Upload resume for analysis
GET /api/resume - Get all user resumes
GET /api/resume/:id - Get specific resume analysis
DELETE /api/resume/:id - Delete resume

----------* Authentication*--------------------



User registration and login with JWT tokens
Secure password hashing
Token-based authentication for protected routes
Automatic token refresh (optional)
------------* Security Features*---------------



JWT authentication
CORS enabled
File upload validation
Password hashing
Input validation and sanitization
Error handling middleware
-------------* Responsive Design*---------------



Mobile-friendly interface
Works on desktop, tablet, and mobile devices
Progressive enhancement

This is about my project if any changes needed or extra features need to add please keep request for it thank you..
