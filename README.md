# Chatbot-for-Innovation 🤖✨

_A lightweight, retrieval-augmented chatbot that lets you “talk” to innovation
reports and datasets._

![Python](https://img.shields.io/badge/python-3.10%2B-blue)
![License: MIT](https://img.shields.io/badge/License-MIT-green)

## What it does
This notebook-driven project turns any PDF (and easily extensible data sources)
into a conversational knowledge base:

1. **Ingest** – Extracts text with **pdfplumber**, chunks it using
   **RecursiveCharacterTextSplitter**, and embeds it with **OpenAI** models.  
2. **Store** – Persists embeddings in a local **Chroma** vector database
   (`./chroma_db`) so you can pick up right where you left off.
3. **Chat** – Runs a `ConversationalRetrievalChain` (LangChain v0.1+) with memory,
   powered by **GPT-4o/3.5** (`ChatOpenAI`), letting you ask follow-up questions
   naturally.
4. **Share (optional)** – Expose the bot to teammates with one command via
   **pyngrok**.

Typical use-cases include rapid policy analysis, literature deep dives, and
interactive Q&A for hackathons or classroom demos.

---

## Quick start

### Prerequisites
* Python ≥ 3.10
* An **OpenAI API key**
* (Optional) Ngrok account & authtoken if you want a public URL
* Git + Jupyter

```bash
# 1. Clone
git clone https://github.com/<your-user>/Chatbot-for-Innovation.git
cd Chatbot-for-Innovation

# 2. Create & activate a virtual env (recommended)
python -m venv .venv
source .venv/bin/activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Configure your key
export OPENAI_API_KEY="sk-..."

# 5. Launch notebook
jupyter notebook Chatbot.ipynb
