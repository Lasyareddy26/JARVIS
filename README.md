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

## ✨ Features at a Glance

| Feature | Description |
|---------|-------------|
| 💬 **AI Chat** | Conversational interface powered by Groq LLM with full context awareness |
| 🎯 **Objective Management** | Ingest goals via text/file, auto-generate step-by-step plans, track progress |
| 📚 **Learnings Capture** | Record insights, mistakes, successes, patterns with semantic tagging |
| ⚖️ **Decision Logging** | Document decisions with reasoning, alternatives, and expected outcomes |
| 🔮 **AI Reflections** | Auto-generated reflective summaries identifying patterns and suggestions |
| 🔍 **Semantic Search** | Vector-based search across all your data using sentence-transformers |
| 🤖 **GuideBot** | Multilingual in-app onboarding assistant to help you navigate |
| 📊 **Dashboard** | Visual overview with charts and progress tracking |
| 📄 **File Ingestion** | Upload PDFs, DOCX files, or paste raw text to create objectives |
| ⚡ **Event-Driven** | Redis Streams-based async event processing for background tasks |

---

## 🔍 What Each Module Does

### 💬 Chat — Your AI Business Partner

Chat is the **central hub** of JARVIS. It's not just a chatbot — it's a thinking partner with memory.

- **Context-aware conversations**: JARVIS remembers every past conversation, learning, failure, and decision. When you discuss a topic, it automatically pulls in relevant history.
- **Auto-capture intelligence**: Just talk naturally. Say *"I decided to raise my rates to $150/hr"* and JARVIS automatically logs it as a Decision. Say *"I learned that cold outreach doesn't work"* and it's captured as a Learning — no forms needed.
- **Smart plan generation**: Say *"I want to launch a newsletter by March"* and JARVIS generates a structured, phased action plan with checkable subtasks — right inside the chat.
- **Proactive warnings**: If you're about to repeat a past mistake, JARVIS will warn you before you do.
- **Persistent sessions**: All conversations are saved to PostgreSQL. Pick up any past conversation from the sidebar.

---

### 📊 Dashboard — Bird's-Eye View of Your Journey

The Dashboard gives you an **instant snapshot** of everything you've built with JARVIS.

- **Summary stats**: See total counts for Objectives, Learnings, Decisions, and Reflections at a glance.
- **Recent objectives**: View your latest goals with their current status (`staging`, `in_progress`, `completed`) and progress bars showing percentage completion.
- **Recent learnings**: Browse your most recent insights, mistakes, and successes with category badges and tags.
- **Recent decisions**: See your latest logged decisions with reasoning summaries.
- **Recent reflections**: View AI-generated reflection summaries and identified patterns.

---

### 🎯 Objectives — Goal Tracking with AI-Generated Plans

Objectives are your **goals broken down into actionable, trackable plans**.

- **Create from anywhere**: Type a goal in Chat (*"I want to build a landing page"*) or use the dedicated "New Objective" button with raw text or file uploads (PDF/DOCX).
- **AI-generated plans**: JARVIS analyzes your goal and auto-generates a multi-phase plan with weighted steps (e.g., Phase 1: Research → Phase 2: Design → Phase 3: Build).
- **Approval workflow**: Review the generated plan, then approve or reject it before execution begins.
- **Step-by-step tracking**: Click any step to mark it complete. The progress bar and percentage update in real-time.
- **Bi-directional sync**: Complete a step in Chat ↔ it updates on the Objectives page, and vice versa.
- **Status lifecycle**: Each objective flows through: `staging` → `planning` → `awaiting_approval` → `approved` → `in_progress` → `completed`.

---

### 📚 Learnings — Your Personal Knowledge Base

Learnings capture **everything you've learned** on your business journey so you never lose an insight.

- **Six categories**: Insights 💡, Mistakes ⚠️, Successes ✅, Patterns 🔄, Tools 🔧, and Process 📋 — each color-coded.
- **Auto-capture from Chat**: Say something like *"I just realized warm intros convert 10x better"* in Chat and JARVIS auto-captures it as a Learning.
- **Manual capture**: Use the "Capture Learning" form to add learnings with category, content, and tags.
- **Smart tagging**: Tag learnings for easy filtering and cross-referencing.
- **Built-in analytics**: Toggle the Analytics view to see interactive charts — bar charts by category, pie charts by tag distribution, and area charts showing learning trends over time (powered by Recharts).
- **Filter & search**: Filter by tag using the dropdown, click any tag on a card to instantly filter, or browse all learnings sorted latest-first.

---

### ⚖️ Decision Log — Document Every Choice You Make

The Decision Log ensures you **never forget why you made a decision** — and whether it worked out.

- **Structured logging**: Each decision records: *What* you decided, *Why* you chose it, the *Context* around it, *Alternatives considered*, and *Expected outcome*.
- **Auto-capture from Chat**: Say *"I decided to go with Stripe over PayPal because..."* in Chat and JARVIS auto-captures the full decision with reasoning.
- **Manual logging**: Use the "Log Decision" form for detailed entries with all fields.
- **Outcome tracking**: Revisit past decisions to check if expected outcomes materialized — learn from what worked and what didn't.
- **Tag-based organization**: Tag decisions by area (pricing, hiring, strategy, etc.) for quick retrieval.

---

### 🔮 Reflections — AI-Powered Self-Analysis

Reflections help you **step back, see the bigger picture**, and identify patterns you might miss day-to-day.

- **AI-generated analysis**: Ask JARVIS to reflect on any topic (e.g., *"How am I handling client communication?"*) and it generates a deep, personalized summary by analyzing your objectives, learnings, and decisions.
- **Pattern identification**: Each reflection highlights recurring patterns JARVIS has noticed across your data (e.g., *"You tend to underestimate timelines for design tasks"*).
- **Actionable suggestions**: Every reflection includes specific, grounded suggestions based on your own history — not generic advice.
- **Trigger from Chat or Reflections page**: Say *"Help me reflect on my pricing strategy"* in Chat, or use the dedicated "New Reflection" button.
- **Historical review**: Browse all past reflections sorted by date to track how your thinking evolves over time.

---

### 🤖 GuideBot — Multilingual Onboarding Assistant

GuideBot is a **floating helper widget** that guides first-time (and returning) users through the app.

- **10 languages supported**: English 🇬🇧, Hindi 🇮🇳, Telugu 🇮🇳, Spanish 🇪🇸, French 🇫🇷, German 🇩🇪, Japanese 🇯🇵, Chinese 🇨🇳, Arabic 🇸🇦, and Portuguese 🇧🇷.
- **Page-aware guidance**: GuideBot knows which page you're on and explains that specific feature — *What it does*, *How to use it*, and *When to use it*.
- **Quick action buttons**: One-click shortcuts like "How do I create an objective?", "Take me to Chat", or "How does auto-capture work?".
- **Pro tips**: Each page explanation comes with curated tips to help you get the most out of the feature.
- **Free-form questions**: Ask GuideBot anything about the app and it responds contextually using the built-in knowledge base.

---

### 🔍 Semantic Search — Find Anything Instantly

Search uses **vector embeddings** to find relevant content across your entire knowledge base.

- **Powered by Sentence-Transformers**: All objectives, learnings, decisions, and reflections are embedded using the `all-MiniLM-L6-v2` model for high-quality semantic matching.
- **Cross-entity search**: A single query searches across all data types simultaneously — not just keyword matching but meaning-based retrieval.
- **Context for Chat**: The Chat AI uses semantic search under the hood to pull in relevant past data before responding, making every answer deeply personalized.

---

### ⚡ Event-Driven Processing — Background Intelligence

Behind the scenes, JARVIS uses **Redis Streams** for async event processing.

- **Non-blocking ingestion**: When you submit a goal, the API responds instantly with a `202 Accepted` while background workers process, analyze, and generate the plan.
- **Event worker pipeline**: A dedicated `EventWorker` listens on Redis Streams, consuming domain events and triggering use cases (plan generation, embedding creation, etc.).
- **Staging → Planning flow**: Objectives go through a staging phase in Redis (with TTL-based expiry), then move to PostgreSQL once the AI plan is generated and ready for approval.

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
