# PaperTrail backend requirements

## Security audit

The frontend uses public OpenAlex and Crossref endpoints and does not contain a private API key. The current AI copilot is deterministic and local; it does not call an LLM. No secrets should be added to this static GitHub Pages repository.

## Static-site limits

GitHub Pages can host the frontend, but it cannot safely hold server secrets. CORE API access requires a server-side key. Reliable arXiv ingestion and high-volume Semantic Scholar/PubMed access should be routed through a backend proxy that can enforce rate limits and caching. A real AI/LLM Research Brief also requires a server endpoint because its provider key must remain private.

## Recommended routes

- GET /api/search?query=...&providers=... — provider fan-out, normalization, deduplication, ranking, caching
- GET /api/citations/:id — references and citing papers from permitted providers
- POST /api/research-brief — synthesize only the selected paper metadata/abstracts
- GET /api/core — server-side CORE proxy with CORE_API_KEY
- Optional authenticated storage routes for cross-device profiles and libraries

Use environment variables for all private keys. Never commit .env files, tokens, or API keys. The current frontend remains usable with public providers and local browser storage while these backend routes are optional.
