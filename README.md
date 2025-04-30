# LangChain-Powered PDF QA Bot

## Overview

This project is the final hands-on assignment in the IBM AI Engineering Professional Certificate. It demonstrates how to build an intelligent Question Answering (QA) bot capable of responding to user queries by understanding and extracting relevant content from uploaded PDF documents. The system leverages the LangChain framework and a Large Language Model (LLM) hosted on IBM Watsonx to retrieve accurate answers based on semantic understanding of the documents.

## Objective

Build a Retrieval-Augmented Generation (RAG) chatbot that:

- Accepts a PDF document.
- Parses and semantically embeds the document.
- Uses a retriever to find relevant text chunks.
- Responds to natural language queries using an LLM.
- Offers a clean user interface via Gradio.

## Key Components

| Component              | Purpose                                                                 |
|------------------------|-------------------------------------------------------------------------|
| `PyPDFLoader`          | Load and parse PDF files into raw text documents.                       |
| `RecursiveCharacterTextSplitter` | Chunk text into manageable pieces while preserving context.  |
| `WatsonxEmbeddings`    | Convert text chunks into vector embeddings using IBM's embedding model. |
| `Chroma`               | Vector database for storing and retrieving semantically similar chunks. |
| `WatsonxLLM`           | IBM-hosted LLM used to generate answers based on retrieved context.     |
| `RetrievalQA`          | LangChain chain to integrate retrieval and generation seamlessly.       |
| `Gradio`               | Frontend interface for uploading documents and submitting queries.      |

## How It Works

1. Document Upload: User uploads a PDF via the Gradio UI.
2. Loading & Chunking: The document is loaded and split into smaller text chunks.
3. Embedding & Storage: Chunks are embedded and stored in a Chroma vector database.
4. Querying: User submits a question.
5. Retrieval & Generation: Relevant chunks are retrieved and passed to the LLM for answer generation.
6. Response: The final answer is displayed in the UI.

## Requirements

You can install the dependencies in a virtual environment with:

```bash
python3.11 -m pip install \
gradio==4.44.0 \
ibm-watsonx-ai==1.1.2  \
langchain==0.2.11 \
langchain-community==0.2.10 \
langchain-ibm==0.1.11 \
chromadb==0.4.24 \
pypdf==4.3.1 \
pydantic==2.9.1
```

## Running the App

To launch the application:

```bash
python qabot.py
```

Then open your browser and go to `http://localhost:7860` to interact with the QA bot.

## Learning Outcomes

By completing this project, you will be able to:

- Integrate multiple tools to build an end-to-end RAG system.
- Use LangChain and IBM Watsonx to solve document-based question-answering tasks.
- Deploy a simple yet powerful NLP app using Gradio.
