# Agentic-RAG-Chatbot
Agentic RAG chatbot leveraging Groq, Supabase, and Streamlit to deliver AI-driven conversations from custom PDF content.

This repository contains the code for an Agentic RAG Chatbot using LangChain, Groq API, Supabase, and Streamlit. Follow the steps below to set up and run the chatbot on your local system.

## Prerequisites
Ensure you have the following installed:
- Python 3.8+
- Git
- Virtual Environment (Optional but recommended)

## Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/Kanishkvijay/Agentic-RAG-Chatbot.git
cd Agentic-RAG-Chatbot
```

### 2. Create a Virtual Environment (Optional but Recommended)
```bash
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Set Up Environment Variables
Create a `.env` file in the root directory and add the following details:
```
GROQ_API_KEY=your_groq_api_key
SUPABASE_URL=your_supabase_url
SUPABASE_SERVICE_KEY=your_supabase_service_key
```
Replace `your_groq_api_key`, `your_supabase_url`, and `your_supabase_service_key` with your actual credentials.

### 5. Set Up Supabase Database
1. Go to your Supabase project dashboard.
2. Open the SQL Editor and paste the content from `supabase.txt`.
3. Run the query to create the necessary database table.

### 6. Upload Documents to Supabase
```bash
python database.py
```
This script processes the PDF files in the `documents` folder and stores them in Supabase.

### 7. Run the Chatbot
```bash
streamlit run agentic_rag_chatbot.py
```
This will start a local server, and you can access the chatbot in your browser.

## Folder Structure
```
Agentic-RAG-Chatbot/
│── documents/            # Folder containing PDF documents
│── agentic_rag_chatbot.py # Main chatbot script
│── database.py           # Script to upload documents to Supabase
│── requirements.txt      # Dependencies
│── supabase.txt          # SQL script for database setup
│── .env                  # Environment variables (to be created by the user)
│── README.md             # Setup instructions
```

## Notes
- Ensure your Supabase project allows vector searches (`pgvector` extension enabled).
- If any dependency fails, try upgrading with `pip install --upgrade <package>`.

Enjoy building your Agentic RAG Chatbot! 🚀
