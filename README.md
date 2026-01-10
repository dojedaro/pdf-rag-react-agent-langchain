# PDF RAG + Zero-Shot ReAct Agent (LangChain)

This repository demonstrates a **two-part LangChain system** combining **Retrieval-Augmented Generation (RAG)** for document question answering and a **Zero-Shot ReAct agent** capable of reasoning and tool use.

The project showcases how large language models can be grounded in external knowledge while also performing multi-step reasoning with external tools.

---

## 🔍 Project Overview

### Part 1 — PDF Question Answering (RAG)
A document-based Q&A pipeline that:
- Loads a PDF document
- Splits text into overlapping chunks
- Embeds chunks using Hugging Face sentence embeddings
- Indexes vectors with **FAISS**
- Answers user questions using only retrieved document context

### Part 2 — Zero-Shot ReAct Agent with Tools
A reasoning agent that:
- Plans actions using natural language reasoning
- Dynamically selects tools
- Combines intermediate results into a final answer

---

## ✨ Key Features

### 📄 Document RAG Pipeline
- PDF ingestion via `PyPDFLoader`
- Recursive text chunking
- Semantic embeddings (Sentence Transformers)
- FAISS vector similarity search
- Context-grounded LLM answers

**Example questions**
- “Summarize the key ideas from this document.”
- “Explain how LangChain supports document-based Q&A.”
- “What are the trade-offs between different retrieval strategies?”

---

### 🤖 Tool-Using ReAct Agent
The agent autonomously selects tools to solve multi-step queries.

**Tools used**
- Wikipedia (factual lookup)
- LLM Math (symbolic calculations)
- Python REPL (post-processing and numeric reasoning)

**Example questions**
- “What is the population of France and its square root?”
- “What is cos(60°) plus ln(10)?”

---

## 🧠 System Architecture

### PDF RAG Flow
User Question  
→ FAISS Retriever  
→ Relevant Document Chunks  
→ LLM  
→ Context-grounded Answer  

### ReAct Agent Flow
User Question  
→ LLM Reasoning  
→ Tool Selection  
→ Tool Execution  
→ Final Answer  
