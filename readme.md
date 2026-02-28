# 🏛️ NyayaAI

<div align="center">

**Production-Grade Multi-Agent AI System for Autonomous Legal Contract Red-Flagging**

*Empowering individuals and businesses to understand legal contracts through AI — focused on Indian Law*

[![Next.js](https://img.shields.io/badge/Next.js-15-black?style=for-the-badge&logo=next.js)](https://nextjs.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.129-009688?style=for-the-badge&logo=fastapi)](https://fastapi.tiangolo.com/)
[![LangGraph](https://img.shields.io/badge/LangGraph-1.0-blue?style=for-the-badge)](https://langchain-ai.github.io/langgraph/)
[![Google Gemini](https://img.shields.io/badge/Gemini-2.5_Flash-4285F4?style=for-the-badge&logo=google)](https://ai.google.dev/)
[![LiveKit](https://img.shields.io/badge/LiveKit-Voice_AI-FF6B6B?style=for-the-badge)](https://livekit.io/)

[Live Demo](https://nyayai-tnn.vercel.app/) • [Youtube Video](https://youtu.be/7AumTu6EZSk)

</div>

---

## 📋 Table of Contents

- [Project Description](#-project-description)
- [Problem Statement](#-problem-statement)
- [Innovation & Unique Approach](#-innovation--unique-approach)
- [Key Features](#-key-features)
- [Bonus Features Attempted](#-bonus-features-attempted)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [API Documentation](#-api-documentation)
- [Usage Guide](#-usage-guide)
- [Live Demo](#-live-demo)

---

## 📖 Project Description

**NyayaAI** is an intelligent, production-grade multi-agent AI system designed to democratize legal understanding for everyday users in India. The platform autonomously analyzes legal contracts (rental agreements, employment contracts, NDAs, service agreements, etc.), identifies potential risks, provides relevant Indian legal references, and suggests balanced alternatives — all without requiring expensive legal consultation.

The system employs a sophisticated **multi-agent architecture** orchestrated through **LangGraph**, where specialized AI agents work in concert to:

1. **Parse & Structure** legal documents from PDF to machine-readable format
2. **Classify** clauses into 13 distinct legal categories
3. **Detect & Score** risks using hybrid LLM + rule-based analysis
4. **Retrieve** relevant Indian law citations (Contract Act 1872, IT Act 2000, Consumer Protection Act, etc.)
5. **Generate** balanced redline suggestions with rationale
6. **Summarize** findings in non-lawyer friendly language
7. **Simulate** negotiations between parties with an AI judge for disputed clauses
8. **Provide** real-time voice-based legal guidance in multiple Indian languages

---

## 🎯 Problem Statement

Legal contracts are ubiquitous yet inherently complex. The average person signing a rental agreement, employment contract, or service agreement often lacks:

- **Legal literacy** to understand complex jargon and implications
- **Financial resources** to consult lawyers for routine contracts
- **Time** to thoroughly review lengthy documents
- **Awareness** of their rights under Indian law

This creates a significant power imbalance where individuals unknowingly agree to unfavorable or even exploitative terms. NyayaAI addresses this gap by providing:

- **Instant** contract analysis within minutes
- **Accessible** explanations in simple language
- **Actionable** suggestions for balanced alternatives
- **Free** or low-cost alternative to legal consultation for routine contracts

---

## 💡 Innovation & Unique Approach

### 1. **Multi-Agent Orchestration via LangGraph**

Unlike monolithic LLM applications, NyayaAI employs a **true multi-agent architecture** where each agent is a specialist:

```
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│ Clause          │ -> │ Risk Detector    │ -> │ Legal Retriever │
│ Classifier      │    │ Agent            │    │ Agent           │
└─────────────────┘    └──────────────────┘    └─────────────────┘
                                │
                                ▼
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│ Summary         │ <- │ Redline          │ <- │ Negotiation     │
│ Agent           │    │ Generator        │    │ Simulator       │
└─────────────────┘    └──────────────────┘    └─────────────────┘
```

This modular approach enables:
- **Specialization**: Each agent is optimized for its specific task
- **Reliability**: Failures in one agent don't cascade to others
- **Scalability**: Agents can be upgraded/replaced independently
- **Explainability**: Clear audit trail of each agent's contribution

### 2. **Hybrid Risk Scoring (LLM + Deterministic Rules)**

We combine the reasoning capabilities of LLMs with deterministic rule-based scoring:

- **LLM Qualitative Analysis**: Understands context, nuance, and intent
- **Rule-Based Scoring**: Consistent, reproducible risk scores based on trigger terms
- **Three-Tier Classification**: High / Medium / Low risk with clear thresholds
- **Smart Tagging**: Only flags clauses with actual risks — standard clauses remain clean

### 3. **India-Focused Legal Context**

Built specifically for Indian legal landscape:
- **Indian Contract Act 1872** compliance checking
- **IT Act 2000** references for digital contracts
- **Consumer Protection Act** awareness
- **State-specific tenancy laws** consideration
- **Real-time web search** for latest legal precedents via DuckDuckGo

### 4. **Conversational Voice AI in Regional Languages**

Breaking language barriers with real-time voice assistance:
- **Hindi, English, Marathi, Hinglish** support
- **LiveKit + Google Gemini** for low-latency voice interactions
- **Document-aware context** — the AI knows your specific contract
- **Noise cancellation** for clear communication

### 5. **Adversarial Negotiation Simulation**

Unique two-party debate system:
- **Party A (Corporate Counsel)**: Defends original contract terms
- **Party B (Reviewing Party)**: Advocates for fairer terms
- **AI Judge**: Evaluates arguments and produces balanced compromise
- **5-round debates** with reasoned conclusions

---

## ✨ Key Features

| Feature | Description |
|---------|-------------|
| 📄 **PDF to Markdown** | Structured extraction preserving document hierarchy (machine-readable PDFs) |
| 🏷️ **Clause Classification** | 13 categories: Termination, Indemnity, Arbitration, Confidentiality, IP, Payment, Liability, Force Majeure, Governing Law, Amendment, Notice, Warranty, Other |
| ⚠️ **Risk Detection** | Three-tier (High/Medium/Low) with detailed issue explanations and trigger terms |
| 📊 **Risk Scoring** | 0-100 deterministic score + qualitative LLM analysis |
| ⚖️ **Legal Citations** | Indian law cross-references with section numbers and explanations |
| ✏️ **Redline Suggestions** | Balanced rewrites with rationale for each change |
| 📝 **Executive Summary** | Non-lawyer friendly contract summary with top risks highlighted |
| 🔍 **Interactive Analysis** | Click-to-highlight risk navigation in document preview |
| 📑 **Version Control** | Original vs Edited markdown comparison |

---

## 🏆 Bonus Features Attempted

### ✅ **1. Real-Time Voice-Based Legal Guidance Assistant**

We implemented a fully functional **voice AI assistant** powered by LiveKit and Google Gemini:

**Technical Implementation:**
- **LiveKit Agents SDK** for real-time audio streaming
- **Google Gemini Realtime Model** for natural language understanding
- **Noise Cancellation** (BVC plugin) for clear audio in noisy environments
- **Server-side context injection** — the voice agent has full access to the analyzed document

**Capabilities:**
- Answers questions about specific clauses in the uploaded contract
- Explains legal jargon in simple terms with real-world examples
- Identifies high/medium/low risk clauses when asked
- Supports **Hindi, English, Marathi, and Hinglish**
- Strictly bound to document context — won't answer unrelated questions

**User Flow:**
1. User uploads and analyzes a contract
2. Clicks "Talk to Nyaya AI" button
3. Voice agent greets and asks for language preference
4. User asks questions verbally about their contract
5. Agent responds with clear, spoken explanations

### ✅ **2. Multi-Party Negotiation Simulation**

We implemented a sophisticated **LangGraph-based negotiation engine**:

**Technical Implementation:**
- **StateGraph** with typed state management
- **Two adversarial agents** (Party A & Party B) with distinct personas
- **AI Judge** that evaluates 5 rounds of debate and produces balanced verdicts
- **WebSocket streaming** for real-time debate updates to frontend

**Personas:**
- **Party A (Corporate Counsel)**: Preserves original terms, maximizes legal protection
- **Party B (Reviewing Party)**: Advocates for balanced changes using suggestions

**Output:**
- Full debate transcript with round-by-round arguments
- Judge's reasoning explaining the decision
- **Balanced replacement clause** that both parties could accept
- Final draft generation with negotiated changes highlighted

---


## 🛠️ Tech Stack

### Backend (AI Pipeline)

| Technology | Purpose |
|------------|---------|
| **Python 3.11+** | Core runtime |
| **LangGraph** | Multi-agent workflow orchestration (MANDATORY) |
| **LangChain** | Agent framework and prompt management |
| **Google Gemini 2.5 Flash** | Primary LLM for all agents |
| **FastAPI** | REST API framework |
| **PyMuPDF4LLM** | PDF to Markdown conversion |
| **Pydantic** | Data validation and serialization |
| **DuckDuckGo Search** | Real-time legal web search |

### Backend (Server)

| Technology | Purpose |
|------------|---------|
| **FastAPI** | REST API + WebSocket server |
| **Motor** | Async MongoDB driver |
| **MongoDB** | User authentication storage |
| **LiveKit API** | Voice room token generation |

### Voice Agent

| Technology | Purpose |
|------------|---------|
| **LiveKit Agents SDK** | Real-time voice pipeline |
| **Google Gemini Realtime** | Voice LLM with streaming |
| **LiveKit Noise Cancellation** | Audio preprocessing |
| **HTTPX** | Async context fetching |

### Frontend

| Technology | Purpose |
|------------|---------|
| **Next.js 15** | React framework with App Router |
| **TypeScript** | Type-safe development |
| **Tailwind CSS** | Utility-first styling |
| **Zustand** | Lightweight state management |
| **React Markdown** | Markdown rendering with custom components |
| **LiveKit React SDK** | Voice UI components |

---

## 📁 Project Structure

```
nyayaai/
│
├── client/                          # Next.js Frontend
│   ├── app/
│   │   ├── page.tsx                 # Landing page with PDF upload
│   │   ├── layout.tsx               # Root layout
│   │   └── (root)/
│   │       ├── analysis/            # Contract analysis view
│   │       ├── negotiation/         # Negotiation simulation view
│   │       └── final-draft/         # Final draft with changes
│   ├── components/
│   │   ├── ui/                      # Reusable UI components
│   │   ├── analysis/                # Analysis-specific components
│   │   │   ├── risk-sidebar.tsx     # Risk cards sidebar
│   │   │   ├── risk-mark.tsx        # Inline risk highlighting
│   │   │   └── md-components.tsx    # Custom markdown renderers
│   │   ├── voice-agent-panel.tsx    # LiveKit voice UI
│   │   └── auth-dialog.tsx          # Authentication modal
│   └── lib/
│       ├── annotations-store.ts     # Risk annotation parser & store
│       ├── negotiation-store.ts     # Negotiation state management
│       └── auth-context.tsx         # Auth context provider
│
├── nyaya_ai/                        # AI Analysis Pipeline
│   ├── agents/
│   │   ├── clause_classifier.py     # Classifies clause types
│   │   ├── risk_detector.py         # Detects and scores risks
│   │   ├── legal_retriever.py       # Finds legal citations
│   │   ├── redline_generator.py     # Generates suggestions
│   │   ├── summary_agent.py         # Creates executive summary
│   │   └── negotiation_simulator.py # Simulates negotiations
│   ├── orchestrator/
│   │   └── workflow.py              # LangGraph workflow definition
│   ├── schemas/
│   │   └── models.py                # Pydantic models
│   ├── api/
│   │   └── app.py                   # FastAPI endpoints
│   ├── risk_engine.py               # Deterministic scoring engine
│   ├── pdf_to_markdown.py           # PDF extraction module
│   └── main.py                      # CLI entry point
│
├── server/                          # Backend Server
│   ├── main.py                      # FastAPI app (auth, upload, negotiation)
│   ├── database.py                  # MongoDB connection
│   └── negotiation.py               # LangGraph negotiation engine
│
├── livekit-voice-agent/             # Voice Agent
│   ├── agent.py                     # LiveKit agent implementation
│   └── pyproject.toml               # Dependencies
│
└── requirements.txt                 # Root dependencies
```

---

## 🚀 Getting Started

### Prerequisites

- **Python 3.11+**
- **Node.js 18+** and **pnpm**
- **MongoDB** (local or Atlas)
- **Google API Key** (Gemini)
- **LiveKit Cloud Account** (for voice features)

### Environment Variables

Create `.env` files in respective directories:

**`nyaya_ai/.env`**
```env
GOOGLE_API_KEY=your_google_api_key
```

**`server/.env`**
```env
GOOGLE_API_KEY=your_google_api_key
GEMINI_API_KEY=your_google_api_key
MONGODB_URI=mongodb://localhost:27017
LIVEKIT_API_KEY=your_livekit_api_key
LIVEKIT_API_SECRET=your_livekit_api_secret
LIVEKIT_URL=wss://your-app.livekit.cloud
```

**`livekit-voice-agent/.env.local`**
```env
GOOGLE_API_KEY=your_google_api_key
LIVEKIT_API_KEY=your_livekit_api_key
LIVEKIT_API_SECRET=your_livekit_api_secret
LIVEKIT_URL=wss://your-app.livekit.cloud
SERVER_URL=http://localhost:8001
```

**`client/.env.local`**
```env
NEXT_PUBLIC_API_URL=http://localhost:8001
NEXT_PUBLIC_AGENT_API_URL=http://localhost:8000
```

### Installation

#### 1. Clone the Repository
```bash
git clone https://github.com/your-repo/nyayaai.git
cd nyayaai
```

#### 2. Setup AI Pipeline (Port 8000)
```bash
cd nyaya_ai
python -m venv venv
# Windows
venv\Scripts\activate
# Linux/Mac
source venv/bin/activate

pip install -r requirements.txt
uvicorn api.app:app --reload --port 8000
```

#### 3. Setup Backend Server (Port 8001)
```bash
cd server
python -m venv venv
venv\Scripts\activate  # or source venv/bin/activate

pip install -r requirements.txt
uvicorn main:app --reload --port 8001
```

#### 4. Setup Voice Agent
```bash
cd livekit-voice-agent
python -m venv venv
venv\Scripts\activate

pip install -e .
python agent.py dev
```

#### 5. Setup Frontend (Port 3000)
```bash
cd client
pnpm install
pnpm dev
```

### Running the Full Stack

Open 4 terminals and run:

| Terminal | Directory | Command |
|----------|-----------|---------|
| 1 | `nyaya_ai/` | `uvicorn api.app:app --reload --port 8000` |
| 2 | `server/` | `uvicorn main:app --reload --port 8001` |
| 3 | `livekit-voice-agent/` | `python agent.py dev` |
| 4 | `client/` | `pnpm dev` |

Access the application at **http://localhost:3000**

---

## 📚 API Documentation

### AI Analysis API (Port 8000)

#### Health Check
```http
GET /health
```
Returns API health status and configuration.

#### Analyze Contract
```http
POST /analyze
Content-Type: multipart/form-data
Body: file (PDF)
```

**Response:**
```json
{
  "job_id": "20260222_143022",
  "overall_risk_score": 67,
  "risk_distribution": {
    "high": 25.0,
    "medium": 45.0,
    "low": 30.0
  },
  "total_clauses": 20,
  "high_risk_count": 5,
  "medium_risk_count": 9,
  "low_risk_count": 6,
  "citations_found": 12,
  "redlines_generated": 14,
  "executive_summary": "...",
  "top_risks": ["..."],
  "files": {
    "annotated_contract": "20260222_143022/annotated_contract.md",
    "risk_report": "20260222_143022/risk_report.json"
  }
}
```

#### Download Analysis Files
```http
GET /download/{job_id}/{filename}
```

### Backend Server API (Port 8001)

#### Authentication
```http
POST /auth/signup
Content-Type: application/json
Body: { "name": "John", "phone": "9876543210" }

POST /auth/signin
Content-Type: application/json
Body: { "phone": "9876543210" }
```

#### Upload PDF
```http
POST /upload
Content-Type: multipart/form-data
Body: file (PDF)
```

#### Generate Final Draft
```http
POST /generate-draft
Content-Type: application/json
Body: {
  "edited_md": "...",
  "replacements": [
    { "original": "old text", "replacement": "new text" }
  ]
}
```

#### LiveKit Token
```http
POST /livekit-token
Content-Type: application/json
Body: { "markdown": "...", "risks": "..." }
```

#### Negotiation WebSocket
```http
WS /negotiate
```
Real-time negotiation streaming with debate messages.

---

## 📖 Usage Guide

### 1. Upload a Contract
- Visit the landing page
- Drag and drop or click to upload a PDF contract
- Sign in with your phone number (first-time users will be registered)

### 2. Review Analysis
- View the parsed contract with highlighted risk sections
- **Red highlights** = High Risk
- **Orange highlights** = Medium Risk
- **Yellow highlights** = Low Risk
- Click any risk card in the sidebar to jump to that clause

### 3. Understand Risks
- Expand risk cards to see:
  - **Flagged Clause**: The problematic text
  - **Suggestion**: Recommended alternative
  - **Legal Reference**: Relevant Indian law section

### 4. Talk to Nyaya AI (Voice)
- Click "Talk to Nyaya AI" in the analysis view
- Allow microphone access
- Ask questions about your contract in Hindi, English, Marathi, or Hinglish
- Get spoken explanations with real-world examples

### 5. Run Negotiation Simulation
- Navigate to the **Negotiation** tab
- Select which risks to negotiate
- Click "Start Negotiation"
- Watch Party A and Party B debate in real-time
- See the AI Judge's balanced verdict

### 6. Generate Final Draft
- Navigate to the **Final Draft** tab
- View the contract with negotiated changes highlighted in green
- Download or copy the balanced contract

---

## 🌐 Live Demo

**Live URL:** *[https://nyayai-tnn.vercel.app](https://nyayai-tnn.vercel.app)*
---

<div align="center">



</div>
