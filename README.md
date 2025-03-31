# Document Summarization & Chatbot Application

## Overview
This project is a **Document Summarization & Chatbot Application** that allows users to:
- Upload a **PDF document**.
- Generate **embeddings** for the document using **HuggingFaceEmbeddings**.
- Store the embeddings in a **Qdrant vector database**.
- Use **Llama 3.2** for answering user queries based on the document content.
- Provide an **interactive chat** experience with the document.

## Features
- **PDF Upload & Preview**: Users can upload a PDF and view it within the interface.
- **Text Embedding & Storage**: The document text is split, embedded, and stored in Qdrant for efficient retrieval.
- **LLM-based Chat**: The chatbot retrieves relevant sections and generates responses using Llama 3.2.
- **Interactive Chat UI**: Users can ask questions and receive intelligent responses from the document.

---

## Installation & Setup Guide
Follow these steps to install and set up the project.

### **1️⃣ Create Virtual Environment**
```sh
python -m venv venv
```
Activate the virtual environment:
- **Windows:**
  ```sh
  venv\Scripts\activate
  ```
- **Mac/Linux:**
  ```sh
  source venv/bin/activate
  ```

### **2️⃣ Install Dependencies**
Install the required dependencies from `requirements.txt`:
```sh
pip install -r requirements.txt
```

### **3️⃣ Download and Run Llama 3.2 Model Using Ollama**
Install **Ollama** from [Ollama's official website](https://ollama.com).

Download the **Llama 3.2:3b** model:
```sh
ollama pull llama3.2:3b
```
Run the model:
```sh
ollama run llama3.2:3b
```
Ensure the model is running before proceeding.

### **4️⃣ Run Qdrant Vector Database (Docker Required)**
```sh
docker run -p 6333:6333 -p 6334:6334 qdrant/qdrant
```
Ensure Qdrant is running before proceeding.

### **5️⃣ Run the Application**
```sh
streamlit run myapp.py
```
This will launch the Streamlit UI where you can upload PDFs and interact with the chatbot.

---

## Project Structure
```
📂 project_root
│── myapp.py                # Main Streamlit UI
│── chatbot.py              # Chatbot logic using Llama 3.2
│── vectors.py              # Handles text embedding & Qdrant storage
│── requirements.txt        # Project dependencies
│── README.md               # Documentation (this file)
```

---

## Dependencies (`requirements.txt`)
Below are the required dependencies for the project.

```txt
streamlit
langchain
pypdf
qdrant-client
sentence-transformers
llama-index
ollama
```

