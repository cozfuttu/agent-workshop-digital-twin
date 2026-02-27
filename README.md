# 🧠 Digital Twin AI Agent

A minimal Retrieval-Augmented Generation (RAG) system that builds a “Digital Twin” capable of professionally representing a person and answering questions about their work without hallucinating.

This project demonstrates how to architect an AI agent using structured knowledge, semantic embeddings, vector search, and controlled generation — rather than relying on prompt stuffing.

---

## 🏗 Architecture

The system consists of four core layers:

### 1️⃣ Knowledge Layer

Structured documents:
- `bio.txt`
- `fluton.txt`
- `legalifi.txt`
- `skills.txt`
- `contact.txt`

Documents are split into semantically meaningful chunks before embedding.


### 2️⃣ Embedding & Memory Layer

- Each chunk is converted into a contextual embedding  
- Embeddings are indexed using **ChromaDB**  
- The vector database acts as the agent’s memory  

### 3️⃣ Retrieval Layer

When a query is received:

- The query is embedded  
- Similarity search retrieves the most relevant chunks  
- Only top-k relevant context is selected  

### 4️⃣ Generation Layer

The LLM receives:

- A strict system prompt (persona + constraints)  
- The retrieved context  
- The user question  

The model is explicitly instructed to:

- Use only provided context  
- Avoid hallucinating  
- Respond professionally and concisely  

---

## 🛠 Tech Stack

- Python 3.10+
- OpenAI API
- ChromaDB
- Streamlit

---

## ⚙️ Installation

### 1️⃣ Clone the repository

```bash
git clone https://github.com/yourusername/digital-twin-agent.git
cd digital-twin-agent
```

### 2️⃣ Create a virtual environment

#### macOS / Linux

```bash
python3 -m venv venv
source venv/bin/activate
```

#### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

### 3️⃣ Install dependencies

```bash
pip install -r requirements.txt
```

### 4️⃣ Set your OpenAI API key

#### macOS / Linux

```bash
export OPENAI_API_KEY=your_key_here
```

#### Windows

```bash
setx OPENAI_API_KEY "your_key_here"
```

### 5️⃣ Run the App

```bash
python -m streamlit run app.py
```

---

## 🤝 Acknowledgment

This project was originally built live during a 90-minute workshop focused on designing reliable AI agents using RAG architecture principles. You can watch the workshop [here](https://x.com/elifhilalumucu/status/2024907344325362057)
