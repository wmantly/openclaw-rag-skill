# Changelog

All notable changes to the OpenClaw RAG Knowledge System will be documented in this file.

## [1.0.0] - 2026-02-11

### Added
- Initial release of RAG Knowledge System for OpenClaw
- Semantic search using ChromaDB with all-MiniLM-L6-v2 embeddings
- Multi-source indexing: sessions, workspace files, skill documentation
- CLI tools: rag_query.py, rag_manage.py, ingest_sessions.py, ingest_docs.py
- Python API: rag_query_wrapper.py for programmatic access
- Automatic integration wrapper: rag_context.py for transparent RAG queries
- RAG-enhanced agent wrapper: rag_agent.py
- Type filtering: search by document type (session, workspace, skill, memory)
- Document management: add, delete, reset collection
- Batch ingestion with intelligent chunking
- Session parser for OpenClaw event format
- Automatic daily updates via cron job
- Comprehensive documentation: README.md, SKILL.md

### Features
- **Semantic Search**: Find relevant context by meaning, not keywords
- **Local Vector Store**: ChromaDB with persistent storage (~100MB per 1,000 docs)
- **Zero Dependencies**: No API keys required (all-MiniLM-L6-v2 is free and local)
- **Smart Chunking**: Messages grouped by 20 with overlap for context
- **Multi-Format Support**: Python, JavaScript, Markdown, JSON, YAML, shell scripts
- **Automatic Updates**: Scheduled cron job runs daily at 4:00 AM UTC
- **State Tracking**: Avoids re-processing unchanged files
- **Debug Mode**: Verbose output for troubleshooting

### Bug Fixes
- Fixed duplicate ID errors by including chunk_index in hash generation
- Fixed session parser to handle OpenClaw event format correctly
- Fixed metadata conversion errors (all metadata values as strings)

### Performance
- Indexing speed: ~1,000 docs/minute
- Search time: <100ms (after embedding load)
- Embedding model: 79MB (cached locally)
- Storage: ~100MB per 1,000 documents

### Documentation
- Complete SKILL.md with OpenClaw integration guide
- Comprehensive README.md with examples and troubleshooting
- Inline help in all CLI tools
- Best practices and limitations documented

---

## [1.0.1] - 2026-02-11

### Added
- `package.json` with complete OpenClaw skill metadata
- `CHANGELOG.md` for version tracking
- `LICENSE` (MIT) for proper licensing

### Changed
- `package.json` explicitly declares NO required environment variables (fully local system)
- Documented data storage path: `~/.openclaw/data/rag/`
- Enhanced `README.md` with clearer installation instructions
- Added references to CHANGELOG, LICENSE, and package.json in README
- Clarified that no API keys or credentials are required

### Documentation
- Improved documentation transparency to meet security scanner best practices
- Clearly documented the fully-local nature of the system (no external dependencies)

---

## [Unreleased]

### Planned
- API documentation indexing from external URLs
- Automatic re-indexing on file system events (inotify)
- Better chunking strategies for long documents
- Integration with external vector stores (Pinecone, Weaviate)
- Webhook notifications for automated content processing
- Hybrid search (semantic + keyword)
- Query history and analytics
- Export/import of vector database

---

## Version Guidelines

This project follows [Semantic Versioning](https://semver.org/):

- **MAJOR** version: Incompatible API changes
- **MINOR** version: Backwards-compatible functionality additions
- **PATCH** version: Backwards-compatible bug fixes

## Categories

- **Added**: New features
- **Changed**: Changes in existing functionality
- **Deprecated**: Soon-to-be removed features
- **Removed**: Removed features
- **Fixed**: Bug fixes
- **Security**: Security vulnerabilities