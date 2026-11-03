# MediScan AI 🩺

MediScan AI is a simple medical report chatbot that allows users to upload a medical PDF and interact with its contents through a chat interface.

The application uses Retrieval-Augmented Generation (RAG) to retrieve relevant information from the uploaded document and generate answers using an LLM.

## Features

- Upload medical reports in PDF format.
- Extract basic patient information, including name, age, gender, patient ID, and diagnosis.
- Ask questions about the uploaded medical report.
- Retrieve relevant information using semantic search.
- Maintain conversation context for follow-up questions.
- Restrict responses to questions related to the uploaded report.
- Display answers through a simple Streamlit interface.

## Tech Stack

- **Python** – Core programming language
- **Streamlit** – User interface
- **LangChain** – LLM integration and document processing
- **Groq** – LLM inference
- **Hugging Face** – Text embeddings
- **ChromaDB** – Vector database
- **PyPDFLoader** – PDF document loading
- **Sentence Transformers** – Embedding model

## Project Structure

```text
MediScan-AI/
│
├── app.py
├── requirements.txt
├── .env.example
├── .gitignore
└── README.md
```

## Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/your-username/MediScan-AI.git
cd MediScan-AI
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

Activate it:

**Windows**
```bash
venv\Scripts\activate
```

**macOS / Linux**
```bash
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure environment variables

Create a `.env` file in the root directory:

```env
GROQ_API_KEY=your_groq_api_key
```

Get your API key from [Groq Console](https://console.groq.com/keys).

### 5. Run the application

```bash
streamlit run app.py
```

The application will open in your browser.

## How It Works

1. Upload a medical report in PDF format.
2. The application extracts text from the document.
3. The extracted content is divided into smaller chunks.
4. Hugging Face embeddings convert the chunks into vectors.
5. ChromaDB stores the vectors for semantic retrieval.
6. When a question is asked, relevant document content is retrieved.
7. Groq generates an answer using the retrieved context and conversation history.

## Note

MediScan AI is an educational project intended for exploring PDF processing, Retrieval-Augmented Generation, and conversational AI.

It is not a medical diagnostic tool and does not replace professional medical advice. Uploaded medical documents may contain sensitive personal information. Use only documents you are authorized to process and avoid uploading real patient records to third-party services without appropriate consent and safeguards.