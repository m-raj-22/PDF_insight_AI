
# PDF Insight AI

PDF Insight AI is a Streamlit-based application that allows users to upload and interact with multiple PDF files using natural language. It leverages Google Generative AI (Gemini), FAISS for vector similarity search, and LangChain for managing the QA chain.

## Features

- Upload and process multiple PDF documents
- Extract and chunk PDF text using LangChain's RecursiveCharacterTextSplitter
- Generate vector embeddings with Google Generative AI Embeddings
- Store and search embeddings using FAISS
- Ask natural language questions and receive context-aware answers using Gemini

## Technologies Used

- Python
- Streamlit
- PyPDF2
- LangChain
- FAISS
- Google Generative AI (Gemini)
- Google Generative AI Embeddings

## Project Structure

```
pdf-insight-ai/
├── app.py                  # Main Streamlit application
├── faiss_index/            # FAISS index files (auto-generated)
├── requirements.txt        # Python dependencies
└── README.md               # Project documentation
```

## Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/pdf-insight-ai.git
cd pdf-insight-ai
```

### 2. Install Dependencies

It’s recommended to use a virtual environment:

```bash
pip install -r requirements.txt
```

### 3. Set Up Your Google API Key

Update your environment variables to include your Google Generative AI API key.

Replace this line in the code:
```python
os.getenv("")
```
with:
```python
os.getenv("GOOGLE_API_KEY")
```

Then set the key in your environment:

**Unix/macOS**
```bash
export GOOGLE_API_KEY="your-api-key"
```

**Windows (Command Prompt)**
```cmd
set GOOGLE_API_KEY=your-api-key
```

Or use a `.env` file with a library like `python-dotenv`.

### 4. Run the App

```bash
streamlit run app.py
```

## How It Works

1. User uploads one or more PDF files.
2. Text is extracted and split into manageable chunks.
3. Embeddings are generated using Google Generative AI.
4. Chunks are stored in a FAISS vector index.
5. The user inputs a question, which is used to search relevant chunks.
6. Gemini processes the question and context to generate a detailed answer.

## Notes

- The FAISS index is saved locally and reused during the session.
- Ensure your API key has access to the Generative AI embedding and chat models.
- This project is meant for educational/demo purposes and may require enhancements for production use.

## License

MIT License
