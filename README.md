# AskGeni 🤖

A conversational AI chatbot that allows you to ask questions about your PDF documents using natural language.

## Overview

AskGeni is a Streamlit-based application that leverages LangChain and Llama 2 to provide an interactive chat interface for querying PDF documents. Simply ask questions, and the AI will retrieve relevant information from your documents to provide accurate answers.

## Features

- 📄 **PDF Document Processing** - Automatically loads and processes PDF files
- 💬 **Conversational Interface** - Chat-based UI for natural interactions 
- 🧠 **AI-Powered Responses** - Uses Llama 2 70B model via Replicate
- 🔍 **Vector Search** - FAISS-based similarity search for accurate context retrieval
- 💾 **Chat History** - Maintains conversation context across questions

## Technology Stack

- **Frontend**: Streamlit
- **LLM Framework**: LangChain
- **Language Model**: Llama 2 70B (via Replicate)
- **Vector Database**: FAISS
- **Embeddings**: HuggingFace (sentence-transformers/all-MiniLM-L6-v2)
- **Document Processing**: PyPDF

## Prerequisites

- Python 3.8+
- Replicate API token

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd askgeni
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Create a `.env` file in the root directory and add your Replicate API token:
```
REPLICATE_API_TOKEN=your_token_here
```

4. Place your PDF files in the `Data/` directory

## Usage

1. Start the application:
```bash
streamlit run app3.py
```

2. Open your browser and navigate to the provided local URL (typically `http://localhost:8501`)

3. Ask questions about your documents in the chat interface

## Project Structure

```
askgeni/
├── app3.py              # Main application file
├── requirements.txt     # Python dependencies
├── .env                 # Environment variables (API keys)
└── Data/                # Directory for PDF documents
    ├── datag.pdf
    └── yolov7.pdf
```

## How It Works

1. **Document Loading**: PDF files are loaded from the `Data/` directory
2. **Text Splitting**: Documents are split into manageable chunks
3. **Embeddings**: Text chunks are converted to vector embeddings
4. **Vector Store**: Embeddings are stored in FAISS for efficient retrieval
5. **Conversational Chain**: LangChain creates a retrieval chain with Llama 2
6. **Query Processing**: User questions are matched against document embeddings
7. **Response Generation**: Relevant context is passed to the LLM for answer generation

## Configuration

The application can be configured by modifying parameters in `app3.py`:

- **Chunk Size**: `chunk_size=1000` (line 84)
- **Temperature**: `temperature=0.01` (line 62)
- **Max Response Length**: `max_length=500` (line 62)
- **Retrieval Results**: `k=2` (line 67)

## License

[Add your license here]

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.
