# GSoC 2026 — QMLHEP: Quantum Circuit Design with LLMs

![Python](https://img.shields.io/badge/Python-3.13+-blue?logo=python&logoColor=white)
![PennyLane](https://img.shields.io/badge/PennyLane-latest-brightgreen?logo=data:image/svg+xml;base64,)
![Orchestral AI](https://img.shields.io/badge/Orchestral_AI-latest-orange)
![DeepSeek](https://img.shields.io/badge/LLM-DeepSeek-purple)
![GSoC](https://img.shields.io/badge/GSoC-2026-red?logo=google)

Evaluation submission for the ML4SCI QMLHEP GSoC 2026 project — **Quantum Circuit Design with LLMs**.

## What this is

A closed-loop **Quantum Architecture Search (QAS)** system powered by an LLM agent (DeepSeek via Orchestral AI). The agent autonomously designs, evaluates, and compares variational quantum circuit (VQC) architectures for MNIST classification across two phases:

- **Phase 1** — Agentic learning rate optimization on a fixed baseline architecture
- **Phase 2** — Architecture search across entanglement topologies (linear, circular, full) and circuit depths, with Frobenius unitary equivalence checking to test whether shallower circuits can replace deeper ones

Five custom Orchestral AI tools are registered: `hilbert_space_dimension`, `train_qnn`, `describe_circuit`, `draw_circuit`, and `check_equivalence`.

## Setup

```bash
git clone https://github.com/rainsfal1/gsoc2026-qmlhep
cd gsoc2026-qmlhep
pip install orchestral-ai pennylane torch torchvision python-dotenv
cp .env.example .env   # add your DeepSeek API key
```

Then run `notebook.ipynb` top to bottom. Works on Colab (prompts for API key) and locally (reads from `.env`).

## Requirements

- Python 3.13+
- DeepSeek API key (free tier works): https://platform.deepseek.com

## Results (seed=42)

| Metric | Architecture | Value |
|---|---|---|
| Best by accuracy | 2L-circular-angle | 31.84% (depth 16) |
| Best by efficiency | 1L-linear-angle | ratio 0.0313 |
| Optimal learning rate | — | 0.10 |
| Frobenius distance (2L-circular vs 1L-circular) | — | 5.77 |
| Frobenius distance (2L-circular vs 1L-linear) | — | 5.61 |

Frobenius distances confirm shallower circuits are structurally distinct from the best performer — not just differently parameterized — justifying the QAS approach over simplification alone.

> All accuracy figures are relative comparisons on a 512-sample MNIST subset. No quantum advantage is claimed.
