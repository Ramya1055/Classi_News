📰 ClassiNews - News Article Classification System

ClassiNews is an AI-powered web application that automatically classifies news articles into 5 categories:

Sports

Technology

Politics

Finance

Entertainment

🎯 Features

✅ High Accuracy – 92% accuracy trained on BBC News dataset

✅ 5 Categories – Focused news classification

✅ Modern Dashboard – Beautiful, colorful UI with real-time stats

✅ Real-time Classification – Instant category prediction with confidence scores

✅ RESTful API – FastAPI backend with batch prediction support

✅ Category Filtering – Filter articles by category

✅ Article Management – Save, view, and delete classified articles

✅ Sample Articles – Pre-loaded examples for testing

📁 Project Structure
ClassiNews/
│
├── backend/
│   ├── app.py
│   ├── model.pkl
│   ├── preprocess.pkl
│   ├── requirements.txt
│   └── saved_articles.json
│
├── frontend/
│   ├── dashboard.html
│   ├── dashboard.js
│   ├── dashboard.css
│   └── news.jpeg
│
├── notebooks/
│   ├── gen_ai_notebook.ipynb
│   └── test.csv
│
└── README.md
🚀 Quick Start
Step 1: Install Dependencies
cd backend
pip install -r requirements.txt
Step 2: Ensure Model Files Exist

Make sure these files are inside backend/:

model.pkl – Trained Multinomial Naive Bayes model

preprocess.pkl – TF-IDF vectorizer

Step 3: Start the Backend Server
cd backend
python app.py

Server will start at:

http://localhost:8002
Step 4: Open the Dashboard

Open:

frontend/dashboard.html

in your browser.

📓 Training the Model
Option 1: AG News Dataset

Download from Kaggle

Place ag_news.csv inside notebooks/

Option 2: BBC News Dataset

Place bbc_articles.csv inside notebooks/

Run:

cd notebooks
python ag_news_training.py

This will:

Load dataset

Preprocess text

Train Multinomial Naive Bayes

Save model.pkl and preprocess.pkl to backend/

🔌 API Endpoints
POST /predict

Request

{
  "text": "Your news article text here..."
}

Response

{
  "category": "Technology",
  "confidence": 95.5
}
POST /predict/batch
{
  "articles": [
    {"text": "Article 1..."},
    {"text": "Article 2..."}
  ]
}
GET /articles/sample

Returns 10 sample articles.

POST /articles/save
{
  "id": "unique-id",
  "text": "Article text...",
  "category": "Sports",
  "confidence": 92.3,
  "timestamp": "2025-12-02T09:30:00"
}
Other Endpoints

GET /articles/saved

DELETE /articles/saved/{id}

GET /health

GET /

🎯 Categories

🏆 Sports

💻 Technology

🏛️ Politics

💰 Finance

🎬 Entertainment

🛠️ Technology Stack
Backend

FastAPI

scikit-learn

joblib

NLTK

Uvicorn

Frontend

HTML5

CSS3

JavaScript

Machine Learning

Algorithm: Multinomial Naive Bayes

Vectorizer: TF-IDF (1–2 ngrams)

Preprocessing: Stemming + stop word removal

Training Data: 50K+ news articles

Accuracy: 92%

❌ Troubleshooting
Backend won’t start?

Check if model.pkl and preprocess.pkl exist

Run: pip install -r requirements.txt

Ensure port 8002 is free

Frontend can’t connect?

Confirm backend is running

Check browser console (F12)

Verify CORS in app.py

📝 Example Usage

Examples:

"Apple announces new AI-powered chip for smartphones" → Technology (95%+)

"The local football team won the championship..." → Sports (92%+)

"Stock markets reached all-time high..." → Finance (90%+)

"Government announces new policies..." → Politics (93%+)

"Latest blockbuster movie breaks box office records..." → Entertainment (91%+)
