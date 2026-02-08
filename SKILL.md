# 🧠 Knowledge Graph V3.0 for OpenClaw

**OpenClaw Skill** - Autonomous Parallel Learning System with Real Web Research

[![OpenClaw Skill](https://img.shields.io/badge/OpenClaw-Skill-blue)](https://clawhub.com)
[![Version](https://img.shields.io/badge/Version-3.0.0-green)]()
[![License](https://img.shields.io/badge/License-MIT-yellow)]()

---

## 📦 OpenClaw Skill

This is an **official OpenClaw skill** that extends OpenClaw's autonomous capabilities with:

- 🤖 **6 Parallel Agents** - Simultaneously learning across tasks
- 🌐 **Real Web Research** - Uses OpenClaw browser for live searches  
- 📊 **Performance Tracking** - Measures improvement from learning
- 💾 **Template Storage** - Reuses code from previous iterations
- 🔄 **Self-Reflection** - Autonomous improvement analysis

## Installation

### Via ClawHub (Recommended)
```bash
clawhub install knowledge-graph-v3
```

### Manual Installation
```bash
git clone https://github.com/clowbot123-arch/knowledge-graph-v3.git
cd knowledge-graph-v3
```

## Usage

### Standard Learning Experiment
```bash
python3 run_v3.py
```

### Extreme Challenge (Stress Test)
```bash
python3 extreme_challenge.py
```

## What It Does

### V3.0 Parallel Learning

1. **Launches 6 autonomous agents** simultaneously:
   - `agent_login` → Python Flask Login System
   - `agent_restapi` → FastAPI REST API
   - `agent_fullstack` → Vue.js + Flask Fullstack
   - `agent_docker` → Dockerized Python App
   - `agent_microservice` → Microservices Gateway
   - `agent_db` → SQLite ORM Layer

2. **Iteration 1**: Agents search the web via OpenClaw browser and learn

3. **Iteration 2-3**: Agents reuse stored templates and execute much faster

### Results

| Metric | Before Learning | After Learning | Improvement |
|--------|----------------|----------------|-------------|
| Task Duration | ~24s | ~0.07s | **97-99% faster** |
| Templates Stored | 0 | 4-22 | Automatic |
| Knowledge Reuse | None | All iterations | Yes |

## Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                    OPENCLAW + KNOWLEDGE GRAPH V3.0              │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   🤖 OpenClaw Agents (6 parallel)                              │
│   ┌─────────────────────────────────────────────────────────┐  │
│   │  Each agent:                                             │  │
│   │  1. Check knowledge graph for templates                 │  │
│   │  2. If empty → Web search via OpenClaw browser          │  │
│   │  3. Generate code from templates                        │  │
│   │  4. Store learned knowledge                             │  │
│   └─────────────────────────────────────────────────────────┘  │
│                                                                 │
│   🧠 Knowledge Graph (SQLite)                                   │
│   ┌─────────────────────────────────────────────────────────┐  │
│   │  Tables:                                                │  │
│   │  • knowledge (templates, sources, confidence)            │  │
│   │  • history (execution logs, durations)                   │  │
│   └─────────────────────────────────────────────────────────┘  │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

## Files

```
knowledge-graph-v3/
├── SKILL.md                    # This file
├── README.md                   # Quick reference
├── run_v3.py                  # Main launcher (1.4KB)
├── autonomous_learning_v3.py  # Core system (5KB)
├── extreme_challenge.py       # Stress test (12KB)
├── data/                       # Generated data
│   ├── graph/knowledge.db     # SQLite database
│   └── templates/             # Generated code
└── results/                   # Experiment results
    └── *.json
```

## Requirements

- **OpenClaw** with browser capability
- Python 3.8+
- Internet connection (for web research)
- SQLite3

## Configuration

No configuration required. Uses OpenClaw's built-in browser automatically.

## Troubleshooting

### "Browser not found"
```bash
openclaw browser start --browser-profile openclaw
```

### "Database locked"
Delete the database and restart:
```bash
rm -rf data/graph/knowledge.db
python3 run_v3.py
```

## License

MIT - See LICENSE file

## Author

Created for OpenClaw - The autonomous AI assistant

---

**Part of the OpenClaw ecosystem** 🦞

For more OpenClaw skills: https://clawhub.com
