# RAG Document Question Answering

A Retrieval-Augmented Generation (RAG) project built with **LangChain, Google Gemini, and FAISS**.

This project loads information from a PDF document, splits the document into smaller chunks, converts those chunks into vector embeddings, stores them in a FAISS vector store, retrieves the most relevant chunks for a user question, and uses Gemini 2.5 Flash to generate an organized answer based only on the retrieved document context.

---

## Project Overview

Traditional LLM applications can generate answers using their general knowledge, but they may not know the information contained in a private or custom document.

This project demonstrates a basic RAG pipeline where the LLM is provided with relevant information retrieved from a document before generating the final response.

### RAG Pipeline

```text
PDF Document
     ↓
PyPDFLoader
     ↓
Document Chunks
     ↓
RecursiveCharacterTextSplitter
     ↓
Gemini Embeddings
     ↓
FAISS Vector Store
     ↓
Similarity Retriever
     ↓
Relevant Document Chunks
     ↓
Prompt + Retrieved Context
     ↓
Gemini 2.5 Flash
     ↓
Final Answer
