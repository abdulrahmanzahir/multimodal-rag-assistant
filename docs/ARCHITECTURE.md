# Architecture Overview

## System Components

### Backend Services

#### API Layer
- FastAPI framework
- RESTful endpoints
- WebSocket support for streaming
- Request validation with Pydantic

#### Ingestion Pipeline
- Document parsing (PDF, images, text)
- Content extraction
- Chunking strategies
- Metadata extraction

#### Retrieval System
- Vector embedding generation
- ChromaDB integration
- Semantic search
- Hybrid search (dense + sparse)

#### LLM Integration
- LangChain orchestration
- OpenAI API integration
- Prompt engineering
- Context management

### Data Flow

```
User Upload → Ingestion → Chunking → Embedding → Vector Store
                                                       ↓
User Query → Embedding → Similarity Search → Context Retrieval
                                                       ↓
                                        LLM Generation → Response
```

## Technology Stack

- **Framework**: FastAPI
- **Vector DB**: ChromaDB
- **LLM**: OpenAI GPT-4
- **Orchestration**: LangChain
- **Document Processing**: PyPDF, Pillow
- **Containerization**: Docker

## Design Patterns

- **Repository Pattern**: Data access abstraction
- **Service Layer**: Business logic separation
- **Dependency Injection**: Loose coupling
- **Async/Await**: Non-blocking operations
