# 🔍 RAG System using Llama3, LangChain & ChromaDB

> Ask questions about **your own documents** — powered by Llama3, LangChain orchestration, and ChromaDB vector storage. No fine-tuning required.

[![Python](https://img.shields.io/badge/Python-3.10+-blue?style=flat-square&logo=python)](https://python.org)
[![LangChain](https://img.shields.io/badge/LangChain-0.2+-green?style=flat-square)](https://langchain.com)
[![ChromaDB](https://img.shields.io/badge/ChromaDB-Vector_DB-orange?style=flat-square)](https://trychroma.com)
[![Llama3](https://img.shields.io/badge/Meta-Llama3-purple?style=flat-square)](https://ai.meta.com/llama/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)](LICENSE)

---

## 📌 What is this?

This project implements a **Retrieval-Augmented Generation (RAG)** pipeline that lets you query your own documents intelligently — even if that information was never part of the LLM's training data.

Instead of fine-tuning the model (which is expensive and slow), RAG works by:
1. **Indexing** your documents into a vector database
2. **Retrieving** the most relevant chunks when you ask a question
3. **Generating** a grounded, accurate answer using Llama3

---

## 🧠 How RAG Works

```
Your Documents
      │
      ▼
 Text Chunking
      │
      ▼
Text Embeddings (HuggingFace)
      │
      ▼
ChromaDB (Vector Store)
      │
   [Query]
      │
      ▼
Semantic Similarity Search
      │
      ▼
Relevant Chunks → LangChain → Llama3
      │
      ▼
   📝 Answer
```

---

## 🚀 Tech Stack

| Component | Technology |
|-----------|------------|
| **LLM** | Meta Llama3 (8B–70B, quantized) |
| **Orchestration** | LangChain |
| **Vector Database** | ChromaDB (local persistent) |
| **Embeddings** | HuggingFace sentence-transformers |
| **Interface** | Jupyter Notebook |
| **Language** | Python 3.10+ |

---

## ✨ Features

- 📄 Load and chunk PDF / text documents automatically
- 🧬 Generate semantic embeddings using HuggingFace models
- 💾 Persist vector store locally with ChromaDB (no re-indexing on restart)
- 🤖 Query using a quantized Llama3 model (runs locally via Kaggle/Ollama)
- 🔗 LangChain RetrievalQA chain for clean orchestration
- 🎯 Accurate, context-grounded answers — no hallucination on out-of-scope queries

---

## 📁 Project Structure

```
RAG-Llama3-LangChain-ChromaDB/
│
├── rag-using-llama3-langchain-and-chromadb.ipynb   # Main notebook
├── requirements.txt                                 # Dependencies
├── data/                                            # Put your documents here
│   └── your_document.pdf
├── chroma_db/                                       # Auto-generated vector store
└── README.md
```

---

## ⚙️ Setup & Installation

### 1. Clone the repo
```bash
git clone https://github.com/Ayush8741/RAG-Llama3-LangChain-ChromaDB.git
cd RAG-Llama3-LangChain-ChromaDB
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Add your documents
Place your PDF or text files inside the `data/` folder.

### 4. Run the notebook
```bash
jupyter notebook rag-using-llama3-langchain-and-chromadb.ipynb
```

---

## 🔧 Key Dependencies

```txt
langchain
langchain-community
chromadb
sentence-transformers
pypdf
transformers
torch
```

---

## 💡 How to Use

1. **Load your document** — point the loader to your PDF/text file
2. **Chunk & embed** — documents are split and stored in ChromaDB
3. **Ask a question** — the system retrieves relevant context and Llama3 generates the answer

```python
# Example usage
query = "What are the key findings in the document?"
result = qa_chain({"query": query})
print(result["result"])
```

---

## 📊 Model Info

**Meta Llama3** is used as the generator:
- Pretrained on **15 Trillion+ tokens**
- Available in **8B and 70B** parameter variants
- Quantized version used here for local inference efficiency
- Significant improvement over Llama2 in reasoning and instruction-following

---

## 🧪 Example Output

```
Question: What is the main topic of this document?

Answer: Based on the provided context, the document discusses...
[Grounded answer from your actual document]
```

---

## 🗺️ Future Improvements

- [ ] Add support for multiple document formats (DOCX, CSV, web URLs)
- [ ] Build a Streamlit / Gradio web UI
- [ ] Add conversation memory for multi-turn Q&A
- [ ] Support OpenAI / Gemini as alternative LLMs
- [ ] Deploy as a REST API using FastAPI

---

## 👨‍💻 Author

**Ayush Jindal**  
B.Tech CSE @ Jaypee Institute of Information Technology, Noida  
[![GitHub](https://img.shields.io/badge/GitHub-Ayush8741-black?style=flat-square&logo=github)](https://github.com/Ayush8741)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-ayush--jindal-blue?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/ayush-jindal-a07920284/)

---

## 📄 License

This project is licensed under the MIT License — feel free to use, modify, and distribute.

---

> ⭐ If you found this useful, consider giving it a star!
