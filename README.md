# AI Research Companion

An AI-powered research assistant that simplifies scientific literature review through semantic search, PDF analysis, and context-aware question answering with citation support.

Developed as a Final Year Engineering Project using **FastAPI**, **React**, **MongoDB**, **ChromaDB**, and **Transformer-based Language Models**.

---

## Features

- Secure user authentication using JWT
- Google OAuth login integration
- Upload and process research papers in PDF format
- Search and retrieve research papers from arXiv
- Context-aware question answering using uploaded documents
- Semantic search powered by ChromaDB vector embeddings
- Persistent chat history for each user
- Dashboard with research activity and usage statistics
- Export chat conversations as PDF
- Responsive React + Vite frontend

---

# System Architecture

```text
                  +----------------------+
                  |   React + Vite UI    |
                  +----------+-----------+
                             |
                             |
                      FastAPI Backend
                             |
          +------------------+------------------+
          |                                     |
     MongoDB                              ChromaDB
(User Data & Chats)                (Vector Embeddings)
          |                                     |
          +------------------+------------------+
                             |
                 Transformer-based Models
           (Embeddings + Context Retrieval)
```

---

# Technology Stack

## Frontend

- React 19
- Vite
- React Router
- Axios
- Framer Motion
- jsPDF

## Backend

- FastAPI
- MongoDB (Motor)
- ChromaDB
- Transformers
- Sentence Transformers
- JWT Authentication
- Google OAuth
- Argon2 Password Hashing

---

# Getting Started

## Clone the Repository

```bash
git clone https://github.com/Srinidhi945/AI_Research_Companion.git
cd AI_Research_Companion
git checkout main
```

---

# Backend Setup

## Create a Virtual Environment

```bash
cd backend
python -m venv venv
```

### Activate the Environment

**Windows**

```bash
venv\Scripts\activate
```

**macOS/Linux**

```bash
source venv/bin/activate
```

### Install Dependencies

```bash
pip install -r requirements_backend.txt
```

### Configure Environment Variables

Create a `.env` file inside the `backend` directory.

```env
MONGO_URL=your_mongodb_connection_string
DB_NAME=ai_research

JWT_SECRET=your_secret_key
JWT_ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=60

GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
GOOGLE_REDIRECT_URI=http://127.0.0.1:8000/auth/google/callback

FRONTEND_URL=http://localhost:5173
```

### Run the Backend

```bash
uvicorn app.main:app --reload
```

The backend server will be available at:

```
http://127.0.0.1:8000
```

API documentation is available at:

```
http://127.0.0.1:8000/docs
```

---

# Frontend Setup

Open a new terminal.

```bash
cd frontend
npm install
```

Create a `.env` file inside the `frontend` directory.

```env
VITE_API_BASE_URL=http://localhost:8000
```

> **Note:** All Vite environment variables must begin with `VITE_`.

### Run the Frontend

```bash
npm run dev
```

The frontend application will be available at:

```
http://localhost:5173
```

---

# Google OAuth Configuration

1. Create an OAuth 2.0 Client ID in the Google Cloud Console.
2. Add the following Authorized Redirect URI:

```
http://127.0.0.1:8000/auth/google/callback
```

3. Copy the generated credentials into the backend `.env` file.

---

# Project Structure

```text
AI_Research_Companion/
│
├── backend/
│   ├── app/
│   ├── routers/
│   ├── services/
│   ├── requirements_backend.txt
│   └── .env
│
├── frontend/
│   ├── src/
│   ├── package.json
│   ├── vite.config.js
│   └── .env
│
└── README.md
```

---

# Development

Start the backend:

```bash
cd backend
uvicorn app.main:app --reload
```

Start the frontend:

```bash
cd frontend
npm run dev
```

---

# Roadmap

- Hybrid Retrieval (BM25 + Semantic Search)
- Cross-Encoder Reranking
- Structured Citation Engine
- Section-Aware Summarization
- Hierarchical Document Summarization
- Docker Deployment
- Cloud Deployment (AWS/GCP)

---
