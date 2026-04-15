# ShopAgent — Semana AI Data Engineer 2026 (Gemini CLI Edition)

## Project Overview
Multi-agent e-commerce AI system built across 4 live nights (April 13-16, 2026).
ShopAgent is an autonomous agent crew that queries structured data (SQL in Postgres)
and semantic data (vectors in Qdrant) to answer business questions.

**Central Question:** *O que eu consigo fazer agora que nao conseguia antes?*

**Docker-First:** Days 1-3 run 100% local. Day 4 migrates to cloud.

## Architecture: The Ledger + The Memory
- **The Ledger (Postgres):** Exact data — revenue, counts, averages, JOINs.
- **The Memory (Qdrant):** Meaning — complaints, sentiment, review themes via RAG.
- **AI Stack:** Python 3.11+, Pydantic, LlamaIndex, LangChain, CrewAI, Chainlit.

## Gemini CLI Guidelines
You are the primary assistant for this project. Adhere to the following:
- **Foundational Mandate:** Use the Knowledge Base (KB) located in `.aide/kb/` (to be treated as `.aide/kb/`) for all technical decisions.
- **Role Assumption:** When performing specialized tasks, assume the persona and follow the instructions of the relevant agent in `.aide/agents/`.
- **Validation:** Always validate data structures with Pydantic and follow clean code patterns as defined in the KB.
- **Portuguese Language:** Use Portuguese for user-facing content, accent words, and slide content as specified in the curriculum.

## Directory Structure
- `gen/`: Data generation (ShadowTraffic + Docker).
- `docs/`: Event documentation and agenda.
- `prompts/`: Sequenced live-coding prompts per day.
- `src/`: Python source code and requirements.
- `presentation/`: HTML slide decks.
- `.aide/kb/`: Knowledge Base (18 domains).
- `.aide/agents/`: Specialized Agent instruction sets.

## Knowledge Base (KB) Usage
Always refer to the following domains in `.aide/kb/` before implementing features:
- **Ingestion:** `shadowtraffic`, `pydantic`.
- **Storage:** `supabase` (Postgres/The Ledger), `qdrant` (The Memory).
- **AI Frameworks:** `llamaindex`, `langchain`, `crewai`.
- **Interface & Ops:** `chainlit`, `langfuse`, `deepeval`.
- **General:** `python`, `architecture`, `testing`, `prompt-engineering`.

## Specialized Agent Personas
When the user asks for specific help, reference these instruction sets:
- **Architecture:** `.aide/agents/ai-ml/genai-architect.md`
- **Data Engineering:** `.aide/agents/ai-ml/ai-data-engineer.md`
- **Prompting:** `.aide/agents/ai-ml/ai-prompt-specialist.md`
- **Review:** `.aide/agents/code-quality/code-reviewer.md`
- **Slides:** `.aide/agents/domain/aide-slide-builder.md`

## Development Conventions
- Python 3.11+ with strict type hints.
- Pydantic for all data validation and LLM structured outputs.
- KB files: concepts < 150 lines, patterns < 200 lines.
- File naming: kebab-case.
- All code must be production-ready with proper error handling.

## Quickstart (Local)
```bash
cd gen
cp .env.example .env
cp license.env.example license.env
# Set API keys and ShadowTraffic license
docker compose up
```
