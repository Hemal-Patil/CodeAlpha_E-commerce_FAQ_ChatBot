# E-commerce FAQ Chatbot

## Overview
An NLP powered E-commerce FAQ Chatbot that quickly answers common questions about orders, payments, shipping, and returns. It matches user queries to a predefined FAQ dataset and provides relevant responses, with a fallback for unrecognized questions. Includes a simple web interface for easy interaction.

---
## Features
- Answer FAQs related to orders, payments, shipping, returns, and account management.
- NLP based question matching useing cosine similarity for accurate responses.
- Handles unrecognized queries gracefully with a fallback message.
- Supports both CLI and web-based interaction.
- Lightweight, easy-to-extend FAQ dataset.
- Responsive chat interface for mobile and desktop devices.

---
## Technologies Used
- Python - Core programming language for backend logic.
- Flask - Web framework for serving the chatbot UI.
- NLTK - NLP library for text preprocessing and tokenization.
- Scikit-learn - Used for vectorization and cosine similarity calculations.
- HTML, CSS, JavaScript - Frontend for chat interface
- Marked.js - For rendering Markdown formatting in answers.
- JSON - FAQ dataset storage format.

---
## Project Structure
```
E-commerce_FAQ_Chatbot/
│
├── chatbot/
│    ├── __init__.py
│    ├── preprocess.py    # text preprocessing
│    ├── vectorize.py     # convert text to vectors
│    └── similarity.py    # compute similarity
│
├── templates/
│   └── index.html        # Main chatbot UI page
│
├── static/
│   ├── script.js         # frontend JS
│   └── style.css         # CSS styling
│
├── app.py                # Flask app
├── main.py               # CLI mode
├── faq_dataset.json      # FAQ dataset
├── requirements.txt
├── .gitignore
└── README.md
```

---
## Installation

1. Clone the repository
```
git clone https://github.com/Hemal-Patil/CodeAlpha_E-commerce_FAQ_ChatBot
cd E-commerce_FAQ_ChatBot
```

2. Create and activate virtual environment (recommended)
```
python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows
```

3. Install dependencies:
```
pip install -r requirements.txt
```

---
## Usage

1. Run with Web UI (Flask)
```
python app.py
```
- Open a browser and go to `http://127.0.0.1:5000`
- Type questions in the chatbox and get FAQ answers

2. Run via CLI
```
python main.py
```
- Type your questions in the terminal
- The bot returns the most relevant answer from the FAQ dataset

---
## Dataset
- FAQs are stored in `faq_dataset.json`
- Each entry contains a `"question"` and its corresponding `"answer"`
To add more FAQs:
Append new entries in same JSON format to the file `faq_dataset.json`:
```
{
  "question": "your question here",
  "answer": "your answer here"
}
```

---
## Working
1. Preprocessing
- FAQ questions and user input are cleaned and tokenized.
- Stopwords removed to improve matching accuracy.

2. Vectorization & Similarity:
- FAQ questions are converted into numerical vectors using TF-IDF.
- User input is vectorized with the same TF-IDF model.
- The vectorized user query is compared against all FAQs using cosine similarity.
- The answer with the highest similarity score is returned.

3. Fallback
- If no FAQ is sufficiently similar, the bot replies with a fallback message.

---
