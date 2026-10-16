# Personal Portfolio AI

An AI-powered personal portfolio backend that enables recruiters to interact with candidate profiles through natural-language questions. Built using FastAPI and Groq LLM, the application parses PDF resumes, extracts structured candidate information, and generates answers grounded in the provided resume data.

## Features

- **PDF Resume Parsing:** Extracts text from candidate resumes using PyPDF.
- **Structured Information Extraction:** Uses Groq LLM and Pydantic schemas to organize resume details into structured JSON.
- **AI-Powered Recruiter Q&A:** Answers candidate-specific questions using extracted resume information.
- **REST API:** Provides endpoints for application status checks and conversational queries.
- **Interactive API Documentation:** Uses FastAPI's Swagger UI for testing endpoints.
- **Resume-Grounded Responses:** Designed to keep answers limited to information available in the candidate's resume.

## Tech Stack

- **Language:** Python
- **Backend Framework:** FastAPI
- **LLM Provider:** Groq
- **PDF Processing:** PyPDF
- **Data Validation:** Pydantic
- **Server:** Uvicorn
- **Communication:** REST APIs, JSON

## Project Structure

```text
Personal-Portfolio-AI/
├── backend/
│   ├── main.py
│   └── ...
├── frontend/
│   └── ...
├── pyproject.toml
└── README.md
```

*Adjust the structure above to match your actual repository.*

## Getting Started

### Prerequisites

- Python 3.10 or a compatible version
- A Groq API key
- `uv` or Python's virtual environment and package management tools

### Installation

1. Clone the repository:

   ```bash
   git clone <your-repository-url>
   cd Personal-Portfolio-AI
   ```

2. Navigate to the backend directory:

   ```bash
   cd backend
   ```

3. Create and activate a virtual environment if you are not using `uv`:

   ```bash
   python -m venv .venv
   ```

   macOS/Linux:

   ```bash
   source .venv/bin/activate
   ```

   Windows:

   ```bash
   .venv\Scripts\activate
   ```

4. Install the project dependencies using your configured dependency manager. If you maintain a `requirements.txt`, run:

   ```bash
   pip install -r requirements.txt
   ```

5. Configure your Groq API key as an environment variable:

   macOS/Linux:

   ```bash
   export GROQ_API_KEY="your_api_key"
   ```

   Windows PowerShell:

   ```powershell
   $env:GROQ_API_KEY="your_api_key"
   ```

   Use the environment-variable name expected by your implementation, and never commit API keys to GitHub.

### Run the Backend

Start the FastAPI development server using Uvicorn:

```bash
uvicorn main:app --reload
```

The exact command may differ depending on your project structure.

Once the server starts, open:

- **API root:** `http://127.0.0.1:8000/`
- **Interactive API documentation:** `http://127.0.0.1:8000/docs`

## API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/` | Checks application status |
| POST | `/chat` | Processes recruiter questions using candidate resume data |

### Example Request

```json
{
  "question": "What programming languages does the candidate know?"
}
```

*The request fields must match your actual Pydantic request model.*

## How It Works

1. The application reads a candidate's PDF resume.
2. PyPDF extracts the text from the document.
3. Groq LLM processes the extracted information into a structured format validated with Pydantic.
4. A recruiter submits a natural-language question through the chat endpoint.
5. The backend uses the structured resume information to generate a candidate-specific response.
6. The response is returned through the REST API.

## Future Improvements

- Build an interactive frontend for recruiter conversations.
- Add job-description and candidate-profile matching scores.
- Improve response evaluation and handling of unsupported questions.
- Add automated API tests and error handling.
- Deploy the application for public access.

## Learning Outcomes

- Building REST APIs with FastAPI
- Integrating hosted LLMs into Python applications
- Extracting and structuring information from PDF documents
- Using Pydantic for schema validation
- Designing prompts for context-grounded AI responses
- Testing API endpoints with Swagger UI

## Disclaimer

This project is intended for learning and demonstration purposes. AI-generated responses may be incomplete or inaccurate and should be verified against the original resume.
