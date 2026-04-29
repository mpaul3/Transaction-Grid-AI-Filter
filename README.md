# Transaction-Grid-AI-Filter
# Fintech Intelligent Workspace

A high-efficiency data workstation for banking transaction management, powered by a local Gemma AI model via Ollama.

## What it does

- Natural language search — type "flagged transactions over £5000" and the grid filters instantly
- AI feedback bar — shows exactly which fields the AI updated and what values were set
- Bulk operations — paste multiple account IDs directly into the search bar
- Action staging — AI-driven bulk updates with a confirmation modal showing all affected records
- Audit log — every action is recorded with the original prompt, filter JSON, affected IDs, and timestamp
- Zero API cost — runs entirely on a local Gemma model via Ollama

## Tech stack

| Layer | Tech |
|---|---|
| Frontend | React + Vite |
| UI | Radix UI + Tailwind + AG Grid |
| State | Zustand |
| Backend | Express |
| Database | SQLite (better-sqlite3) |
| AI | Ollama + Gemma3 (local) |

## Prerequisites

- Node.js 18+
- Ollama installed — [ollama.com](https://ollama.com)
- Gemma3 model pulled

## Setup

### 1. Pull Gemma
\`\`\`bash
ollama pull gemma3
\`\`\`

### 2. Install backend
\`\`\`bash
cd backend
npm install
node seed.js
node index.js
\`\`\`

### 3. Install frontend
\`\`\`bash
cd frontend
npm install
npm run dev
\`\`\`

### 4. Open
\`\`\`
http://localhost:5173
\`\`\`

## Architecture

\`\`\`
Natural Language Input
        ↓
Gemma3 (local, free) — intent detection
        ↓
JSON filter or function call
        ↓
Express backend — validates and executes
        ↓
SQLite database — deterministic truth
        ↓
React grid — renders results
\`\`\`

## Roadmap

- Iteration 1 — Semantic Filter
- Iteration 2 — UI Controller
- Iteration 3 — The Auditor
- Iteration 4 — The Referee (SQL validation layer)
- Iteration 5 — Batch Runner (QA suite)

