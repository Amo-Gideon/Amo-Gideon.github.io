---
title: Campus Knowledge Base RAG Chatbot
date: 2025-11-01
tags:
  - LLM
  - RAG
---

A retrieval-augmented chatbot that answers questions about campus life and procedures
from a local knowledge base, built with LangChain, Ollama, Chroma, and Gradio.

<!--more-->

Documents are chunked, embedded, and stored in a local Chroma vector database. User
queries are retrieved and grounded into a locally hosted LLM via Ollama through a
LangChain pipeline, with a Gradio web interface for interactive use. The system runs
fully locally, keeping sensitive campus documents off external APIs.
