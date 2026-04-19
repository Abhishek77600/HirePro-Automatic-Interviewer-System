# 🎯 AI Interview Platform

An intelligent hiring platform that automates the entire recruitment process using AI - from resume screening to conducting interviews and generating evaluation reports.

## 📖 About

This platform revolutionizes the hiring process by combining AI-powered automation with human decision-making. Companies can post jobs, and the system automatically screens candidates, conducts virtual interviews, and provides detailed performance reports - all while maintaining fairness and efficiency.

**Key Highlights:**
- 🤖 AI-powered resume screening using Google Gemini
- 🎥 Automated video interviews with proctoring
- 📊 Intelligent candidate evaluation and scoring
- 📧 Automated email notifications
- 📄 Professional PDF reports
- 🔒 Secure and scalable architecture

## ✨ Features

### For Recruiters (Admin)
- Create and manage job postings
- AI-powered candidate shortlisting
- Send automated interview invitations
- Review AI-generated interview reports
- Accept/reject candidates with one click
- Track application status in real-time

### For Candidates
- Browse available job openings
- Apply with resume (PDF/DOCX)
- Receive interview invitations via email
- Take AI-proctored virtual interviews
- Get instant feedback and scores
- Track application status

### AI Capabilities
- Resume analysis and matching
- Dynamic interview question generation
- Real-time answer evaluation
- Comprehensive performance reports
- Proctoring with tab-switch detection

## 🛠️ Tech Stack

- **Backend**: Flask (Python)
- **Database**: PostgreSQL (Render Cloud)
- **AI Engine**: Google Gemini API
- **Email Service**: Resend API
- **PDF Generation**: ReportLab
- **Frontend**: HTML, Tailwind CSS, JavaScript
- **Deployment**: Render

## 🚀 Quick Setup

### Prerequisites
- Python 3.8 or higher
- Git
- A Google account (for Gemini API)
- A Resend account (for emails)

### Step 1: Clone Repository
```bash
git clone <your-repo-url>
cd render-demo
```

### Step 2: Create Virtual Environment
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# Mac/Linux
python3 -m venv venv
source venv/bin/activate
```

### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 4: Get API Keys

#### 🔑 Google Gemini API Key (Required)
1. Go to [Google AI Studio](https://aistudio.google.com/app/apikey)
2. Sign in with your Google account
3. Click **"Create API Key"**
4. Copy the key (starts with `AIzaSy...`)

#### 📧 Gmail SMTP Setup (Required)
1. Go to [Google Account Security](https://myaccount.google.com/security)
2. Enable **2-Step Verification** (if not already enabled)
3. Go to [App Passwords](https://myaccount.google.com/apppasswords)
4. Generate a new app password for **"Mail"**
5. Copy the 16-character password (remove spaces)

#### 🗄️ Database Setup (Choose One)

**Option A: Render Cloud Database (Recommended)**
1. Go to [Render Dashboard](https://render.com/dashboard)
2. Click **"New +"** → **"PostgreSQL"**
3. Name: `interview-db`, Plan: **Free**
4. Click **"Create Database"**
5. Copy the **"External Database URL"**

**Option B: Local PostgreSQL**
```bash
# Install PostgreSQL, then:
createdb hiring_platform
# Use: postgresql://postgres:password@localhost:5432/hiring_platform
```

### Step 5: Configure Environment

Create a `.env` file in the project root:

```env
# Flask Configuration
FLASK_SECRET_KEY=your-secret-key-here
FLASK_DEBUG=True
FLASK_HOST=0.0.0.0
FLASK_PORT=5001

# Database (use your Render database URL or local)
DATABASE_URL=postgresql://user:password@host:5432/database

# Google Gemini AI
GEMINI_API_KEY=AIzaSy...your-key-here

# Gmail SMTP
GMAIL_USER=your-email@gmail.com
GMAIL_APP_PASSWORD=abcdefghijklmnop
```

**Generate a secure secret key:**
```bash
python -c "import os; print(os.urandom(24).hex())"
```

### Step 6: Run the Application
```bash
python app.py
```

Visit: **http://localhost:5001** 🎉

## 📋 How to Use

### For Recruiters

1. **Register as Admin**
   - Click "Admin" tab on login page
   - Sign up with company details

2. **Create Job Posting**
   - Use quick templates (Frontend, Backend, DevOps, Data Scientist)
   - Or paste your own job description
   - Click "Create Job Posting"

3. **Review Applications**
   - Candidates will apply through the candidate portal
   - Click **"AI Shortlist"** to automatically screen resumes

4. **Send Interview Invites**
   - Click **"Send Invite"** for shortlisted candidates
   - Candidate receives email with interview link

5. **Review Results**
   - Download PDF reports after interviews
   - Click **"Accept"** or **"Reject"**

### For Candidates

1. **Register as Candidate**
   - Click "Candidate" tab on login page
   - Sign up with your details

2. **Apply to Jobs**
   - Browse available openings
   - Click "View & Apply"
   - Upload resume (PDF/DOCX)

3. **Take Interview**
   - Check email for interview invitation
   - Click the link to start
   - Allow camera/microphone access
   - Answer AI-generated questions

4. **Track Status**
   - View application status in dashboard
   - Receive email if accepted

## 📊 Project Structure

```
render-demo/
├── app.py                    # Main Flask application
├── requirements.txt          # Python dependencies
├── render.yaml              # Render deployment config
├── .env                     # Environment variables (create this)
├── .env.example             # Environment template
├── .gitignore              # Git ignore rules
├── README.md               # This file
├── test_email.py           # Email testing utility
├── test_improvements.py    # App testing utility
└── templates/              # HTML templates
    ├── login.html          # Login/Register page
    ├── admin_dashboard.html    # Admin portal
    ├── candidate_dashboard.html # Candidate portal
    └── interview.html      # Interview interface
```

## 🐛 Troubleshooting

**Database connection error?**
- Verify `DATABASE_URL` in `.env`
- Check if PostgreSQL is running (local)
- Ensure Render database is active (cloud)

**Email not sending?**
- Verify `GMAIL_USER` and `GMAIL_APP_PASSWORD` in `.env`
- Ensure 2-Step Verification is enabled on your Google account
- Generate a new App Password if needed
- Run `python test_gmail.py` to test

**AI not working?**
- Verify `GEMINI_API_KEY` in `.env`
- Check API quota at [Google AI Studio](https://aistudio.google.com)
- Review console logs for errors

**Port already in use?**
- Change `FLASK_PORT` in `.env` to `5002` or another port

## 🎉 Ready to Go!

Your AI Interview Platform is ready. Start hiring smarter today! 🚀

**Next Steps:**
1. Run `python app.py`
2. Visit http://localhost:5001
3. Create an admin account
4. Post your first job
5. Start interviewing candidates!

