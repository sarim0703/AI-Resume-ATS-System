# AI-Resume-ATS-System

# ATS Resume Scorer

An AI-powered Applicant Tracking System (ATS) Resume Scorer that analyzes resumes against job descriptions and provides an ATS compatibility score, category-wise analysis, and actionable improvement suggestions.

## Overview

The ATS Resume Scorer helps job seekers understand how well their resume matches a specific job description.

Users can upload a resume in PDF, DOC, or DOCX format and provide a job description. The system processes the resume, extracts relevant information, compares it with the job requirements using NLP and semantic similarity techniques, and generates an overall ATS score with detailed feedback.

## Features

- Resume upload with support for PDF, DOC, and DOCX formats
- Job description input for resume-to-JD matching
- Automated resume parsing and information extraction
- NLP-based resume analysis
- Semantic similarity matching using Sentence Transformers
- Skill and keyword matching
- ATS compatibility analysis
- Category-wise scoring and feedback
- LLM-powered resume improvement suggestions
- Skill validation and recommendations
- Resume analysis history
- User authentication using Supabase
- PDF report generation
- Interactive Streamlit dashboard

## Tech Stack

### Frontend
- Streamlit
- Python

### Backend
- FastAPI
- Python
- REST APIs

### NLP & Machine Learning
- spaCy
- Sentence Transformers
- `all-MiniLM-L6-v2`
- BERT
- Semantic Similarity
- NLP-based text processing

### LLM
- Groq API
- Llama 3

### Database & Authentication
- Supabase
- PostgreSQL
- Supabase Authentication

### PDF & Templating
- WeasyPrint
- Jinja2

### Development Tools
- Git
- GitHub
- Jupyter Notebook
- VS Code

## How It Works

```text
Resume + Job Description
          │
          ▼
   Resume Parsing
          │
          ▼
   Text & Skill Extraction
          │
          ▼
   NLP Processing
          │
          ▼
 Semantic Similarity Matching
          │
          ▼
   ATS Score Calculation
          │
          ├── Keywords
          ├── Skills
          ├── Content
          ├── Formatting
          └── ATS Compatibility
          │
          ▼
   Detailed Feedback
          │
          ▼
LLM-Powered Recommendations

Project Structure

AI-Resume-ATS-System/
│
├── backend/
│   ├── api/
│   ├── core/
│   ├── database/
│   ├── models/
│   ├── services/
│   ├── templates/
│   ├── utils/
│   └── main.py
│
├── frontend/
│   ├── components/
│   ├── services/
│   ├── views/
│   ├── .streamlit/
│   └── streamlit_app.py
│
├── jupyter notebooks/
│   ├── 01_EDA_and_DATA_prep.ipynb
│   ├── 02_BERT_EMBEDDINGS.ipynb
│   └── 03_BERT_FINETUNEipynb.ipynb
│
├── requirements.txt
├── .gitignore
└── README.md

## Installation

1. Clone the Repository
git clone https://github.com/sarim0703/AI-Resume-ATS-System.git
cd AI-Resume-ATS-System
2. Create a Virtual Environment
python -m venv venv
Windows
venv\Scripts\activate
3. Install Dependencies
pip install -r requirements.txt

Install the spaCy language model:

python -m spacy download en_core_web_md
Environment Variables

Create a .env file in the project root.

SUPABASE_URL=your_supabase_url
SUPABASE_KEY=your_supabase_service_role_key
SUPABASE_ANON_KEY=your_supabase_anon_key

AUTH_REDIRECT_URL=http://localhost:8501

SENTENCE_TRANSFORMER_MODEL=all-MiniLM-L6-v2

GROQ_API_KEY=your_groq_api_key

For the Streamlit frontend, configure:

frontend/.streamlit/secrets.toml

Do not commit .env or secrets.toml to GitHub.

Running the Application
Start the Backend

From the project root:

uvicorn backend.main:app --reload --host 0.0.0.0 --port 8000

The FastAPI backend will be available at:

http://localhost:8000

API documentation:

http://localhost:8000/docs
Start the Frontend

Open another terminal, activate the virtual environment, and run:

streamlit run frontend/streamlit_app.py

The Streamlit application will be available at:

http://localhost:8501


## NLP & Matching Pipeline

The application combines multiple NLP techniques to evaluate resume-job compatibility.

Resume Processing

Uploaded resumes are parsed and converted into structured text for further analysis.

Semantic Matching

Sentence Transformers are used to generate embeddings and measure semantic similarity between resume content and job-description requirements.

Skill Analysis

Relevant skills and keywords are extracted and compared with the requirements of the job description.

ATS Scoring

The system combines multiple analysis categories to produce an overall ATS compatibility score and detailed feedback.

LLM Feedback

The Groq API with Llama 3 is used to generate actionable suggestions based on identified gaps in the resume.

Jupyter Notebooks

The project includes notebooks covering:

Exploratory Data Analysis and data preparation
BERT-based embeddings
BERT fine-tuning

These notebooks are primarily intended for experimentation and machine-learning development.

Security

Sensitive configuration files are intentionally excluded from version control.

The repository's .gitignore excludes:

.env
frontend/.streamlit/secrets.toml
__pycache__/
backend/logs/

Never publish API keys, authentication tokens, Supabase service-role keys, or other credentials to GitHub.

Future Improvements
Improve resume parsing for complex document layouts
Add additional resume formats
Enhance scoring accuracy with larger datasets
Improve skill extraction and validation
Add more advanced job-specific recommendations
Deploy the application for public access
Add automated testing and CI/CD workflows
Author

Sarim

GitHub:
https://github.com/sarim0703

This project was developed as an AI/NLP-focused resume analysis system combining FastAPI, Streamlit, NLP, semantic similarity, Supabase, and LLM-based feedback.

