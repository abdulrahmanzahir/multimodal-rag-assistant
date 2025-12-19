# Multimodal RAG Assistant

A Retrieval-Augmented Generation (RAG) system that processes and queries multimodal content including text, images, and documents.

## Features

- 📄 Multi-format document ingestion (PDF, images, text)
- 🔍 Vector-based semantic search
- 🤖 LLM-powered intelligent responses
- 🎨 Multimodal content processing
- 🚀 FastAPI backend with async support
- 🐳 Docker containerization

## Project Structure

```
multimodal-rag/
├── backend/           # Python FastAPI backend
│   ├── app/
│   │   ├── api/       # API endpoints
│   │   ├── core/      # Configuration & utilities
│   │   ├── ingestion/ # Document processing
│   │   ├── retrieval/ # Vector search
│   │   ├── services/  # Business logic
│   │   ├── models/    # Data models
│   │   └── tests/     # Test suite
│   ├── pyproject.toml
│   └── Dockerfile
├── frontend/          # Frontend application
├── infra/             # Infrastructure config
│   └── docker-compose.yml
├── docs/              # Documentation
└── .github/workflows/ # CI/CD pipelines
```

## Prerequisites

- Python 3.10+
- Docker & Docker Compose
- OpenAI API key (or other LLM provider)

## Quick Start

### Using Docker Compose

1. Clone the repository
2. Set environment variables:
   ```bash
   export OPENAI_API_KEY=your_api_key_here
   ```
3. Start services:
   ```bash
   cd infra
   docker-compose up -d
   ```
4. Access the API at `http://localhost:8000`

### Local Development

1. Install Poetry:
   ```bash
   curl -sSL https://install.python-poetry.org | python3 -
   ```

2. Install dependencies:
   ```bash
   cd backend
   poetry install
   ```

3. Run the development server:
   ```bash
   poetry run uvicorn app.main:app --reload
   ```

## API Documentation

Once running, visit:
- Swagger UI: `http://localhost:8000/docs`
- ReDoc: `http://localhost:8000/redoc`

## Testing

```bash
cd backend
poetry run pytest
```

## Architecture

### Backend Components

- **API Layer**: FastAPI endpoints for ingestion and retrieval
- **Ingestion Pipeline**: Processes multimodal documents
- **Vector Store**: ChromaDB for semantic search
- **LLM Integration**: OpenAI/LangChain for generation
- **Services**: Business logic orchestration

### Data Flow

1. Documents ingested via API
2. Content extracted and chunked
3. Embeddings generated and stored
4. Query triggers semantic search
5. Retrieved context sent to LLM
6. Generated response returned

## Configuration

Configure via environment variables or `.env` file:

```env
OPENAI_API_KEY=your_key
ENVIRONMENT=development
CHROMA_HOST=localhost
CHROMA_PORT=8001
```

## Contributing

1. Create a feature branch
2. Make your changes
3. Add tests
4. Submit a pull request

## License

MIT License - see LICENSE file for details
