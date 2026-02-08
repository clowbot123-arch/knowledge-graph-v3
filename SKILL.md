# 🧠 Knowledge Graph V3.0 for OpenClaw

**OpenClaw Skill** - External Brain for LLM Code Generation

[![OpenClaw Skill](https://img.shields.io/badge/OpenClaw-Skill-blue)](https://clawhub.com)
[![Version](https://img.shields.io/badge/Version-3.0.0-green)]()
[![License](https://img.shields.io/badge/License-MIT-yellow)]()

---

## 📦 OpenClaw Skill

This is an **official OpenClaw skill** that gives the LLM a persistent external brain for:

- 💾 **Store Code Templates** - Remember useful code patterns
- 🔍 **Query Templates** - Retrieve relevant code when needed
- 🧠 **Learn from Experience** - Confidence scores and usage tracking
- 📊 **Self-Reflection** - Record insights and improvements
- 🔄 **Persistent Across Sessions** - Knowledge survives restarts

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

## 🎯 For LLM: How to Use the Brain

```python
from llm_brain import LLMBrain

brain = LLMBrain()

# 1. Query a template
templates = brain.query("flask_login")
if templates:
    code = templates[0]["content"]
    brain.record_usage(templates[0]["id"])
    print(code)

# 2. Search for code
results = brain.search("authentication patterns")

# 3. Get best template
best = brain.get_best("api_design")

# 4. Store new knowledge
brain.store(
    task_type="vue_auth",
    content=vue_code,
    description="Vue authentication component",
    tags=["vue", "auth"],
    framework="Vue.js",
    language="javascript"
)

# 5. Add reflection
brain.add_reflection(
    "Vue Composition API is cleaner than Options API",
    context="vue_auth_component"
)

# 6. Get stats
stats = brain.get_stats()
```

## 🚀 Running the Systems

### Standard Learning Experiment
```bash
python3 run_v3.py
```
6 parallel agents learning simultaneously with web research.

### Extreme Challenge (Stress Test)
```bash
python3 extreme_challenge.py
```
E-Commerce Microservices Platform with K8s, Terraform, CI/CD.

## 📊 Results

| System | Before Learning | After Learning | Improvement |
|--------|----------------|----------------|-------------|
| V3.0 Parallel | ~24s/task | ~0.07s/task | **97-99% faster** |
| Extreme Challenge | 60s | 0.09s | **99.9% faster** |
| Knowledge Stored | 0 | 4-22 items | Automatic |

## Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                    OPENCLAW + LLM BRAIN                        │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   🤖 LLM (You)                                                 │
│   ┌─────────────────────────────────────────────────────────┐  │
│   │  • Query templates before coding                       │  │
│   │  • Store useful patterns after coding                  │  │
│   │  • Add reflections on what worked                     │  │
│   │  • Search for related knowledge                        │  │
│   └─────────────────────────────────────────────────────────┘  │
│                                                                 │
│   🧠 LLMBrain (SQLite)                                         │
│   ┌─────────────────────────────────────────────────────────┐  │
│   │  Tables:                                               │  │
│   │  • knowledge (templates, confidence, usage count)     │  │
│   │  • reflections (self-learning insights)                │  │
│   │  • sessions (tracking over time)                       │  │
│   └─────────────────────────────────────────────────────────┘  │
│                                                                 │
│   🌐 OpenClaw Browser                                          │
│   ┌─────────────────────────────────────────────────────────┐  │
│   │  • Real web searches for learning                      │  │
│   │  • Source citation & confidence scoring                │  │
│   └─────────────────────────────────────────────────────────┘  │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

## Files

```
knowledge-graph-v3/
├── SKILL.md                    # This file
├── README.md                   # Quick reference
├── llm_brain.py                # ⭐ NEW: LLM External Brain (16KB)
├── run_v3.py                   # Parallel agents launcher
├── autonomous_learning_v3.py    # Core learning system
├── extreme_challenge.py         # Stress test
├── data/
│   ├── llm_brain.db            # SQLite knowledge base
│   └── templates_llm/          # Stored templates
└── results/                    # Experiment results
```

## Requirements

- **OpenClaw** with browser capability
- Python 3.8+
- SQLite3
- Internet connection (for web research)

## Configuration

No configuration required. Uses OpenClaw's built-in browser automatically.

## API Reference

### LLMBrain Methods

| Method | Description |
|--------|-------------|
| `store(task_type, content, ...)` | Store a template |
| `query(task_type)` | Get templates by type |
| `search(query)` | Search across all knowledge |
| `get_best(task_type)` | Get highest confidence template |
| `get_related(task_type)` | Find related knowledge |
| `record_usage(item_id)` | Track template usage |
| `add_reflection(text, context)` | Add self-learning |
| `get_reflections()` | Get recent insights |
| `get_stats()` | Get knowledge base statistics |

## Troubleshooting

### "Database locked"
```bash
rm -f data/llm_brain.db
python3 llm_brain.py  # Recreate with demo
```

### "Browser not found"
```bash
openclaw browser start --browser-profile openclaw
```

## License

MIT - See LICENSE file

## Author

Created for OpenClaw - The autonomous AI assistant

---

**Part of the OpenClaw ecosystem** 🦞

For more OpenClaw skills: https://clawhub.com
