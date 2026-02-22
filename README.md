<p align="center">
  <img src="https://img.shields.io/badge/JARVIS-Personal%20Business%20Assistant-blueviolet?style=for-the-badge&logo=robot&logoColor=white" alt="JARVIS Badge"/>
</p>

<h1 align="center">🤖 J.A.R.V.I.S.</h1>
<h3 align="center"><em>Just A Rather Very Intelligent System</em></h3>
<p align="center">Your AI-powered personal business assistant for objectives, learnings, decisions, and reflections.</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.13-3776AB?style=flat-square&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/FastAPI-0.100+-009688?style=flat-square&logo=fastapi&logoColor=white"/>
  <img src="https://img.shields.io/badge/React-18.3-61DAFB?style=flat-square&logo=react&logoColor=black"/>
  <img src="https://img.shields.io/badge/PostgreSQL-15-4169E1?style=flat-square&logo=postgresql&logoColor=white"/>
  <img src="https://img.shields.io/badge/Redis-7-DC382D?style=flat-square&logo=redis&logoColor=white"/>
  <img src="https://img.shields.io/badge/Docker-Compose-2496ED?style=flat-square&logo=docker&logoColor=white"/>
  <img src="https://img.shields.io/badge/Groq-LLM-FF6600?style=flat-square&logo=lightning&logoColor=white"/>
</p>

---

## 📸 Screenshots

<details>
<summary><strong>🏠 Dashboard</strong></summary>
<br/>
<p align="center">
  <img src="screenshots/dashboard.png" alt="Dashboard" width="90%"/>
</p>
</details>

<details>
<summary><strong>💬 Chat with JARVIS</strong></summary>
<br/>
<p align="center">
  <img src="screenshots/chat.png" alt="Chat View" width="90%"/>
</p>
</details>

<details>
<summary><strong>🎯 Objectives Tracker</strong></summary>
<br/>
<p align="center">
  <img src="screenshots/objectives.png" alt="Objectives View" width="90%"/>
</p>
</details>

<details>
<summary><strong>📚 Learnings</strong></summary>
<br/>
<p align="center">
  <img src="screenshots/learnings.png" alt="Learnings View" width="90%"/>
</p>
</details>

<details>
<summary><strong>⚖️ Decision Log</strong></summary>
<br/>
<p align="center">
  <img src="screenshots/decisions.png" alt="Decisions View" width="90%"/>
</p>
</details>

<details>
<summary><strong>🔮 Reflections</strong></summary>
<br/>
<p align="center">
  <img src="screenshots/reflections.png" alt="Reflections View" width="90%"/>
</p>
</details>

<details>
<summary><strong>🤖 GuideBot Widget</strong></summary>
<br/>
<p align="center">
  <img src="screenshots/guidebot.png" alt="GuideBot Widget" width="90%"/>
</p>
</details>

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| 💬 **AI Chat** | Conversational interface powered by Groq LLM with full context awareness |
| 🎯 **Objective Management** | Ingest goals via text/file, auto-generate step-by-step plans, track progress |
| 📚 **Learnings Capture** | Record insights, mistakes, successes, patterns with semantic tagging |
| ⚖️ **Decision Logging** | Document decisions with reasoning, alternatives, and expected outcomes |
| 🔮 **AI Reflections** | Auto-generated reflective summaries identifying patterns and suggestions |
| 🔍 **Semantic Search** | Vector-based search across all your data using sentence-transformers |
| 🤖 **GuideBot** | In-app onboarding assistant to help you get started |
| 📊 **Dashboard** | Visual overview with charts and progress tracking |
| 📄 **File Ingestion** | Upload PDFs, DOCX files, or paste raw text to create objectives |
| ⚡ **Event-Driven** | Redis Streams-based async event processing for background tasks |

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                     🖥️ Frontend (React)                     │
│          Vite • React 18 • Recharts • Lucide Icons          │
│                      Port 3000                              │
└──────────────────────────┬──────────────────────────────────┘
                           │ REST API
┌──────────────────────────▼──────────────────────────────────┐
│                   ⚡ Backend (FastAPI)                       │
│                      Port 8000                              │
│  ┌───────────────────────────────────────────────────────┐  │
│  │  Interface Layer   │  routes.py (API endpoints)       │  │
│  ├───────────────────────────────────────────────────────┤  │
│  │  Application Layer │  Use Cases & Event Workers       │  │
│  │                    │  • Ingest, Chat, Search           │  │
│  │                    │  • Learnings, Decisions           │  │
│  │                    │  • Reflections, Progress          │  │
│  ├───────────────────────────────────────────────────────┤  │
│  │  Domain Layer      │  Models, Events, Business Logic  │  │
│  ├───────────────────────────────────────────────────────┤  │
│  │  Infrastructure    │  Adapters & External Services    │  │
│  │                    │  • AI (Groq LLM)                 │  │
│  │                    │  • PostgreSQL + SQLAlchemy        │  │
│  │                    │  • Redis Streams                  │  │
│  │                    │  • Sentence-Transformers          │  │
│  └───────────────────────────────────────────────────────┘  │
└──────┬────────────────────────────────┬─────────────────────┘
       │                                │
┌──────▼──────┐                 ┌───────▼───────┐
│ 🐘 Postgres │                 │  🔴 Redis     │
│   Port 5432 │                 │   Port 6379   │
└─────────────┘                 └───────────────┘
```

---

## 🚀 Quick Start

### Prerequisites

- [Docker](https://docs.docker.com/get-docker/) & [Docker Compose](https://docs.docker.com/compose/install/)
- A [Groq API Key](https://console.groq.com/) (free tier available)

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/Lasyareddy26/JARVIS.git
cd JARVIS
```

### 2️⃣ Set Up Environment Variables

```bash
cp .env.example .env
```

Edit `.env` and add your Groq API key:

```env
GROQ_API_KEY=your-actual-groq-api-key
```

### 3️⃣ Launch with Docker Compose

```bash
docker compose up --build -d
```

This spins up **4 services**:

| Service | URL | Description |
|---------|-----|-------------|
| **Frontend** | [http://localhost:3000](http://localhost:3000) | React UI |
| **Backend** | [http://localhost:8000](http://localhost:8000) | FastAPI server |
| **PostgreSQL** | `localhost:5432` | Primary database |
| **Redis** | `localhost:6379` | Event streaming |

### 4️⃣ Verify Everything Is Running

```bash
docker compose ps
```

All services should show `healthy` / `running`.

---

## 📁 Project Structure

```
JARVIS/
├── 📄 docker-compose.yml        # Multi-service orchestration
├── 📄 Dockerfile                 # Backend container
├── 📄 requirements.txt           # Python dependencies
├── 📄 .env.example               # Environment template
├── 📄 streamlit_app.py           # Streamlit alternative UI
│
├── 🐍 backend/                   # FastAPI Application
│   ├── main.py                   # App entry point & lifespan
│   ├── config.py                 # Pydantic settings
│   ├── domain/                   # 🧠 Business Logic
│   │   ├── models.py             # Objective, Learning, Decision, Reflection
│   │   └── events.py             # Domain event definitions
│   ├── ports/                    # 🔌 Interfaces (contracts)
│   │   └── interfaces.py        # Abstract repository & service ports
│   ├── infrastructure/           # 🏭 External Adapters
│   │   ├── ai_adapter.py         # Groq LLM integration
│   │   ├── postgres_adapter.py   # PostgreSQL repositories
│   │   ├── redis_adapter.py      # Redis Streams pub/sub
│   │   ├── embedding_adapter.py  # Sentence-transformers embeddings
│   │   ├── database.py           # SQLAlchemy async engine
│   │   └── input_adapter.py      # PDF/DOCX/text parsing
│   ├── application/              # ⚙️ Use Cases
│   │   ├── ingest_use_case.py    # Process raw input → objective
│   │   ├── chat_use_case.py      # AI chat with context
│   │   ├── search_use_case.py    # Semantic search
│   │   ├── learning_use_case.py  # Capture learnings
│   │   ├── decision_use_case.py  # Log decisions
│   │   ├── reflection_use_case.py# Generate reflections
│   │   ├── event_worker.py       # Background event processor
│   │   └── container.py          # Dependency injection
│   └── interface/                # 🌐 API Layer
│       └── routes.py             # REST endpoints
│
└── ⚛️  frontend/                  # React Application
    ├── Dockerfile                # Frontend container
    ├── package.json              # Node dependencies
    ├── vite.config.js            # Vite bundler config
    └── src/
        ├── App.jsx               # Root component & routing
        ├── api.js                # Backend API client
        ├── styles.css            # Global styles
        ├── context/
        │   └── AppContext.jsx    # Global state management
        └── components/
            ├── ChatView.jsx      # AI chat interface
            ├── DashboardView.jsx # Analytics dashboard
            ├── ObjectivesView.jsx# Objective management
            ├── LearningsView.jsx # Learnings tracker
            ├── DecisionsView.jsx # Decision log
            ├── ReflectionsView.jsx# Reflections viewer
            ├── Sidebar.jsx       # Navigation sidebar
            ├── GuideBotWidget.jsx# Onboarding assistant
            └── ToastContainer.jsx# Notification toasts
```

---

## 🔌 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/v1/ingest/text` | Create objective from text |
| `POST` | `/api/v1/ingest/file` | Create objective from PDF/DOCX |
| `GET` | `/api/v1/objectives/{id}/status` | Check objective status |
| `POST` | `/api/v1/objectives/{id}/approve` | Approve generated plan |
| `PUT` | `/api/v1/objectives/{id}/progress` | Update step progress |
| `GET` | `/api/v1/objectives` | List all objectives |
| `POST` | `/api/v1/learnings` | Capture a learning |
| `GET` | `/api/v1/learnings` | List all learnings |
| `POST` | `/api/v1/decisions` | Log a decision |
| `GET` | `/api/v1/decisions` | List all decisions |
| `POST` | `/api/v1/reflections` | Generate reflection |
| `GET` | `/api/v1/reflections` | List all reflections |
| `POST` | `/api/v1/search` | Semantic search |
| `POST` | `/api/v1/chat` | Chat with JARVIS |
| `GET` | `/api/v1/chat/sessions` | List chat sessions |
| `GET` | `/api/v1/chat/sessions/{id}` | Get chat history |

---

## 🛠️ Tech Stack

### Backend
| Technology | Purpose |
|------------|---------|
| **FastAPI** | Async REST API framework |
| **SQLAlchemy** (async) | ORM & database management |
| **PostgreSQL 15** | Relational data storage |
| **Redis 7** | Event streaming (Redis Streams) |
| **Groq** | LLM inference (Llama models) |
| **Sentence-Transformers** | Local embedding generation |
| **Pydantic** | Data validation & settings |

### Frontend
| Technology | Purpose |
|------------|---------|
| **React 18** | UI component library |
| **Vite 6** | Build tool & dev server |
| **Recharts** | Data visualization & charts |
| **Lucide React** | Icon library |

### Infrastructure
| Technology | Purpose |
|------------|---------|
| **Docker Compose** | Multi-container orchestration |
| **Alpine Linux** | Lightweight container base |

---

## ⚙️ Environment Variables

| Variable | Required | Default | Description |
|----------|----------|---------|-------------|
| `GROQ_API_KEY` | ✅ | — | Your Groq API key for LLM |
| `POSTGRES_URL` | ❌ | `postgresql+asyncpg://postgres:postgres@localhost:5432/webthon` | Database connection |
| `REDIS_URL` | ❌ | `redis://localhost:6379/0` | Redis connection |
| `EMBEDDING_MODEL` | ❌ | `all-MiniLM-L6-v2` | Sentence-transformer model |

---

## 🧪 Local Development (Without Docker)

### Backend

```bash
# Create virtual environment
python -m venv venv
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Set environment variables
cp .env.example .env
# Edit .env with your values

# Run the backend
uvicorn backend.main:app --reload --host 0.0.0.0 --port 8000
```

### Frontend

```bash
cd frontend

# Install dependencies
npm install

# Start dev server
npm run dev
```

> **Note:** You'll need PostgreSQL and Redis running locally, or update the connection strings in `.env`.

---

## 🤝 Contributing

Contributions are welcome! Feel free to:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Commit** your changes (`git commit -m 'Add amazing feature'`)
4. **Push** to the branch (`git push origin feature/amazing-feature`)
5. **Open** a Pull Request

---

## 📜 License

This project is open source and available under the [MIT License](LICENSE).

---

<p align="center">
  <strong>Built with ❤️ by <a href="https://github.com/Lasyareddy26">Lasya Reddy</a></strong>
</p>

<p align="center">
  <em>⭐ Star this repo if you find it helpful!</em>
</p>
