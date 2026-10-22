# Language Translator using LangChain, Groq & FastAPI

A simple LLM-powered language translation application built using LangChain, Groq, FastAPI, and LangServe. The application accepts text and a target language, then generates a translation using a large language model.

## Features

- **LLM Integration:** Uses Groq's API with the `openai/gpt-oss-20b` model.
- **Prompt Engineering:** Uses LangChain's `ChatPromptTemplate` to structure translation requests.
- **Output Parsing:** Uses `StrOutputParser` to return clean text output.
- **REST API:** Exposes the translation chain through FastAPI and LangServe.
- **API Documentation:** Provides interactive API documentation through Swagger UI.
- **Learning Notebook:** Includes a Jupyter Notebook exploring different approaches, coding techniques, and library usage.

## Tech Stack

- Python
- LangChain
- Groq API
- FastAPI
- LangServe
- Uvicorn
- Python-dotenv
- Jupyter Notebook

## Project Structure

```text
basicLLMApp/
├── serve.py              # Main application
├── requirements.txt      # Project dependencies
├── .env                  # API keys (not committed)
├── .env.example          # Example environment configuration
├── learning.ipynb        # Learning notebook and experiments
└── README.md             # Project documentation
```

## Setup and Installation

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd basicLLMApp
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

Activate it on Windows:

```powershell
.venv\Scripts\Activate.ps1
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure environment variables

Create a `.env` file in the project root:

```env
GROQ_API_KEY=your_groq_api_key
```

Get your API key from the [Groq Console](https://console.groq.com/).

**Important:** Never commit your actual `.env` file or expose your API key publicly.

### 5. Run the application

```bash
python serve.py
```

The server will start at:

http://localhost:8000

## API Usage

### Interactive API Documentation

Open the following URL in your browser:

http://localhost:8000/docs

### Invoke the Translation Chain

**Endpoint:** `POST /chain/invoke`

**Example request:**

```json
{
  "input": {
    "language": "French",
    "text": "Hello, how are you?"
  }
}
```

**Example response:**

```json
{
  "output": "Bonjour, comment allez-vous?"
}
```

The exact translation may vary depending on the model's response.

## Learning Notebook

The included Jupyter Notebook documents the learning process behind this application, including:

- Different ways to create prompts and invoke language models.
- Exploring LangChain components and libraries.
- Experimenting with alternative implementations of similar functionality.
- Understanding how prompts, models, and output parsers work together.

## What I Learned

- Building LLM applications using LangChain.
- Creating reusable prompt templates.
- Connecting to hosted LLMs through Groq.
- Composing processing pipelines using LangChain Expression Language (LCEL).
- Exposing LangChain chains as REST APIs using LangServe.
- Managing API credentials with environment variables.
- Running and testing APIs using FastAPI and Swagger UI.

## Future Improvements

- Add a web-based user interface.
- Support translation history.
- Add input validation and error handling.
- Support multiple model providers.
- Add automated tests for the translation API.

## License

This project is intended for educational and learning purposes.
