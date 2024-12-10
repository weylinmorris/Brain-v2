# Second Brain

A self-hosted, block-based note-taking system with automated knowledge discovery.

## Core Features

### Note Taking
- Block-based editing (like Logseq)
- Seamless quick capture on all devices
- Rich text editing with Markdown support
- Support for images, code blocks, and LaTeX
- Automatic metadata capture (location, device, context)
- Version history for all content

### Knowledge Graph
- Bidirectional linking between blocks
- Automated concept extraction and linking
- Visual graph exploration
- Contextual backlinks and references
- Hierarchical organization with infinite nesting

### AI-Powered Analysis
- Automated concept extraction and tagging
- Semantic similarity detection
- Pattern recognition in note-taking behavior
- Unexpected connection discovery
- Content summarization and synthesis
- Topic modeling and clustering

### Personal Knowledge Feed
- Daily resurfacing of relevant past notes
- Smart suggestions based on current context
- "On this day" memories
- Knowledge gaps identification
- Learning path suggestions

## Project Structure

```
second-brain/
├── apps/
│   ├── web/                    # Next.js frontend
│   │   ├── app/               # App router pages
│   │   ├── components/        # React components
│   │   └── lib/              # Utilities and hooks
│   └── ai/                    # AI analysis service
│       ├── api/              # FastAPI service
│       ├── workers/          # Background workers
│       └── models/           # ML model definitions
├── packages/
│   ├── db/                    # Database operations & migrations
│   │   ├── migrations/       # Neo4j migrations
│   │   └── seeds/           # Test data
│   ├── core/                  # Shared business logic
│   │   ├── types/           # TypeScript types
│   │   └── utils/           # Shared utilities
│   └── config/               # Shared configuration
├── docker/                    # Docker configurations
│   ├── dev/                 
│   └── prod/
├── docs/                      # Documentation
└── scripts/                   # Utility scripts
```

## Technology Stack

### Frontend (apps/web)
- Next.js 14+ with App Router
- TypeScript
- TailwindCSS for styling
- Lucide React for icons
- CodeMirror for text editing
- React Flow for graph visualization
- SWR for data fetching
- PWA support for offline capability

### AI Service (apps/ai)
- FastAPI for real-time analysis
- Celery for background tasks
- Redis for task queue
- ML tools:
  - Hugging Face transformers
  - spaCy
  - scikit-learn

### Database & Infrastructure
- Neo4j (graph database)
- Redis (caching & task queue)
- Docker Compose
- Prometheus + Grafana

## Quick Start

1. Prerequisites
   - Docker and Docker Compose
   - Node.js 18+
   - Python 3.10+

2. Installation
   ```bash
   # Clone repository
   git clone https://github.com/yourusername/second-brain.git
   cd second-brain

   # Copy environment files
   cp .env.example .env

   # Start infrastructure
   docker compose up -d

   # Install dependencies
   pnpm install  # or npm install

   # Start development servers
   pnpm dev      # or npm run dev
   ```

3. Access the application:
   - Web UI: http://localhost:3000
   - Neo4j Browser: http://localhost:7474
   - Monitoring: http://localhost:3001 (Grafana)

## Development

### Running Individual Services

```bash
# Frontend only
cd apps/web
pnpm dev

# AI service only
cd apps/ai
python -m uvicorn api.main:app --reload

# Background workers
cd apps/ai
celery -A workers.celery worker --loglevel=info
```

### Environment Variables

See [.env.example](.env.example) for required environment variables.

## Core Features

[Previous features section remains the same...]

## Deployment

The entire stack can be deployed using Docker Compose:

```bash
# Production deployment
docker compose -f docker/prod/docker-compose.yml up -d
```

See [DEPLOYMENT.md](./docs/DEPLOYMENT.md) for detailed instructions.

## Data Model

See [DATA_MODEL.md](./docs/DATA_MODEL.md) for detailed information about:
- Block structure
- Metadata schemas
- Relationship types
- Query patterns
- Index recommendations

## Contributing

1. Fork the repository
2. Create a feature branch
3. Submit a pull request

See [CONTRIBUTING.md](./CONTRIBUTING.md) for detailed guidelines.

## License

MIT License - see [LICENSE](LICENSE)
