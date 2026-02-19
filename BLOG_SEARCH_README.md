<div align="center">

# 🔍 Agentic RAG · AI Blog Search

### *Search smarter. Not harder.*

*Stop skimming. Ask a question — get the exact answer from any blog, instantly.*

</div>

---

## 💡 What Is This?

Most blog search tools match keywords. This one understands meaning.

**AI Blog Search** is an **Agentic RAG** (Retrieval-Augmented Generation) application that fetches any blog post, processes it into a searchable knowledge base, and lets you ask natural language questions — getting back precise, contextually grounded answers.

The secret? It doesn't just retrieve — it *thinks*. A **LangGraph-powered agent** decides whether your query is ready, needs refinement, or requires another retrieval pass before answering. Every response is earned, not guessed.

```python
workflow = {
    "input"     : "A blog URL + your question in plain English",
    "retrieval" : "Qdrant vector DB finds the most semantically relevant chunks",
    "grading"   : "Gemini evaluates if retrieved content actually answers the query",
    "refinement": "Poorly formed queries get automatically rewritten and retried",
    "output"    : "A grounded, accurate answer — not hallucination"
}
```

---

## 🔄 How the Agent Thinks

```
User Query
    │
    ▼
┌─────────────────────┐
│   Vector Retrieval   │  ← Qdrant fetches semantically similar chunks
└────────┬────────────┘
         │
         ▼
┌─────────────────────┐
│  Relevance Grading   │  ← Gemini scores: is this chunk actually useful?
└────────┬────────────┘
         │
    ┌────┴────┐
    │         │
  YES        NO
    │         │
    ▼         ▼
 Answer   Query Rewrite → Retrieve Again
```

No shortcuts. No hallucinated answers. The agent keeps iterating until the retrieval is actually good enough to answer with confidence.

---

## ✨ Features

**🗄️ Vector-Powered Retrieval**
Blog content is chunked, embedded, and stored in **Qdrant** — queries are matched by semantic similarity, not keyword overlap.

**🤖 Agentic Query Processing**
A LangGraph state graph drives the decision loop — retrieve, grade, refine, or answer. The agent chooses the right path automatically.

**📊 Relevance Grading**
Every retrieved chunk is scored by **Gemini** for actual relevance before being used in an answer. Low-quality retrievals get discarded.

**✍️ Automatic Query Refinement**
Vague or poorly structured queries get rewritten by the agent for better retrieval — no frustrating "no results found."

**🌐 Live Blog Ingestion**
Paste any blog URL — **LangChain WebBaseLoader** fetches and processes it in real time, no manual data prep needed.

**🎯 Clean Streamlit UI**
A minimal, distraction-free interface. Paste URL, enter query, get answer.

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Agent Orchestration** | LangGraph |
| **LLM Framework** | LangChain |
| **Embeddings** | Google Gemini `embedding-001` |
| **Chat Model** | Google Gemini `gemini-2.0-flash` |
| **Vector Database** | Qdrant |
| **Blog Ingestion** | LangChain WebBaseLoader |
| **Text Splitting** | RecursiveCharacterTextSplitter |
| **User Interface** | Streamlit |
| **Language** | Python 3.10+ |

---

## 🚀 Getting Started

**1. Install dependencies**
```bash
pip install -r requirements.txt
```

**2. Launch the app**
```bash
streamlit run app.py
```

**3. Use it**
```
① Paste your Google API Key in the sidebar
② Drop in any blog post URL
③ Ask your question in plain English
④ Get a precise, sourced answer
```

---

## 📁 Project Structure

```
agentic-rag-blog-search/
├── app.py               # Streamlit UI and entry point
├── graph.py             # LangGraph workflow and agent logic
├── retriever.py         # Qdrant vector store setup and retrieval
├── grader.py            # Relevance grading with Gemini
├── requirements.txt     # Dependencies
└── README.md            # You are here
```

---

## 🌍 Connect

Built by someone who thinks search should actually work.

**📬 ragashreya09@gmail.com**

<div align="center">

*If you're building in the RAG or LLM agents space — let's talk.*

</div>
