# 🧠 RAG-Powered Enterprise Assistant

An end-to-end **Retrieval-Augmented Generation (RAG)** system that transforms internal documents into an intelligent conversational assistant.  
This Proof of Concept simulates a real enterprise scenario where employees can query internal policies, reports, guidelines, or manuals using natural language, powered by vector search + LLM reasoning.

---

## 🚀 Features

- Load and process enterprise documents (PDF/TXT)
- Automatic chunking and embedding generation
- Vector store creation using **FAISS**
- RAG pipeline implemented with **LangChain**
- Backend API using **FastAPI**
- Web UI using **Streamlit**
- Source-aware answers with retrieved evidence
- Modular architecture for enterprise PoC development

---

## 🏗️ Architecture Overview

### **1. Document Ingestion**  
- Load PDFs/TXTs  
- Split into semantic chunks  
- Generate embeddings using OpenAI  
- Store them in a FAISS vector index  

### **2. Retrieval-Augmented Generation**  
- Retrieve relevant chunks via vector search  
- Feed them to an LLM  
- Generate grounded, context-aware answers  

### **3. Application Layer**  
- API (FastAPI)  
- UI (Streamlit)

---

## 📁 Project Structure

```
rag-enterprise-assistant/
│
├── data/
│   └── docs/                 # Internal documents (PDF/TXT)
│
├── src/
│   ├── ingest.py             # Build vector index from documents
│   ├── rag_pipeline.py       # Retrieval + LLM QA pipeline
│   └── api.py                # FastAPI app
│
├── app/
│   └── ui.py                 # Streamlit web interface
│
├── .env.example              # Environment variable template
├── requirements.txt
└── README.md
```

---

## ⚙️ Installation

```
git clone https://github.com/YOUR_USER/rag-enterprise-assistant.git
cd rag-enterprise-assistant

python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate

pip install -r requirements.txt
```

Create your `.env` file:

```
cp .env.example .env
# Add your OPENAI_API_KEY inside
```

Add your documents to:

```
data/docs/
```

---

## 🧩 Build the Vector Store

```
python -m src.ingest
```

---

## 🤖 Run the Backend API

```
uvicorn src.api:app --reload
```

---

## 🌐 Run the Streamlit UI

```
streamlit run app/ui.py
```

---

## 🧪 Example Questions

You can ask:

- "What are the main obligations under the EU AI Act?"
- "Summarize the core principles of the OECD AI Principles."
- "What risks does NIST identify for AI systems?"
- "What are acceptable water quality levels according to WHO?"
- "What does UNESCO recommend regarding ethical AI?"

---

## 🔮 Future Improvements

- Evaluation notebook for retrieval quality  
- Multi-vector retrievers (colBERT, E5, bge-large)  
- Hybrid search (BM25 + dense retriever)  
- Reranking models  
- Deployment on GCP (Cloud Run / Vertex AI)  
- Authentication for enterprise use  

---

# 📜 Licenses & Attributions

This project includes public documents used for research, experimentation and educational purposes as part of a Retrieval-Augmented Generation (RAG) proof of concept.  
All documents are publicly available and included in accordance with their respective licenses.

---

### **1. European Union Artificial Intelligence Act (Regulation (EU) 2024/1689)**
Public legal document of the European Union.

**Source:** EUR-Lex, Official Journal of the European Union  
**Link:** https://eur-lex.europa.eu  
**License:** Public domain under EU Open Data Policy

---

### **2. Gobernar con la Inteligencia Artificial: panorama actual y hoja de ruta**
© OECD. Licensed under Creative Commons Attribution 4.0 International (CC BY 4.0).

**Source:** Organisation for Economic Co-operation and Development (OECD)  
**License:** CC BY 4.0  
**Attribution:** © OECD, licensed under CC BY 4.0.

---

### **3. NIST AI Risk Management Framework (AI RMF 1.0)**
A United States Government publication. Not subject to copyright.

**Source:** National Institute of Standards and Technology (NIST)  
**License:** Public Domain (U.S. Government Work)

---

### **4. UNESCO – Recommendation on the Ethics of Artificial Intelligence**
Licensed under Creative Commons Attribution-NonCommercial-ShareAlike 3.0 IGO (CC BY-NC-SA 3.0 IGO).

**Source:** UNESCO  
**License:** CC BY-NC-SA 3.0 IGO  
**Attribution:** © UNESCO. This material is shared for non-commercial, educational and research purposes.

---

### **5. WHO Drinking Water Quality Guidelines (Extracts)**  
Open-access content from the World Health Organization, redistributed with attribution.

**Source:** World Health Organization (WHO)  
**License:** Open Access (attribution required)  
**Attribution:** © World Health Organization.  

---


All rights remain with the original authors and institutions.  
This repository uses these materials **solely for educational and experimental AI purposes**.
