# RAG Chatbot with Conversational Memory

A Retrieval-Augmented Generation (RAG) chatbot that lets you upload documents and ask conversational questions over them. It uses LangChain, ChromaDB, and OpenAI, with a FastAPI backend and a Streamlit frontend.

## Tech Stack

- Backend: FastAPI, LangChain, ChromaDB, SQLite
- Frontend: Streamlit
- Models: OpenAI (GPT-4o-mini or compatible)
- Language: Python 3.9+

## Setup

1. Clone the repo and install dependencies:

   ```bash
   git clone https://github.com/YOUR-USERNAME/rag-chatbot.git
   cd rag-chatbot
   pip install -r requirements.txt

2. Create .env in the project root:

    ```bash
   OPENAI_API_KEY=your_openai_api_key

## Running the App

1. Start the FastAPI backend:
   
   ```bash
   cd api
   uvicorn main:app --reload --port 8000

2. Start the Streamlit frontend (in a new terminal):

   ```bash
   cd app
   streamlit run streamlit_app.py --server.port 8500

3. Open the UI at: http://localhost:8500

## How It Works

1. Upload PDF/DOCX/HTML files in the sidebar.
2. The backend chunks the text, embeds it, and stores it in ChromaDB.
3. Your questions are answered by retrieving relevant chunks and passing them, plus chat history, to the LLM.
4. Conversation memory is keyed by session ID so follow-up questions stay in context.
