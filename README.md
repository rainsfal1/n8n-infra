# GSoC 2026 — QMLHEP: Quantum Circuit Design with LLMs

Evaluation submission for the ML4SCI QMLHEP GSoC 2026 project.

## What this is
A closed-loop Quantum Architecture Search (QAS) system using Orchestral AI.
The agent autonomously designs, evaluates, and compares variational quantum
circuit architectures for MNIST classification.

## Setup
1. Clone the repo
2. Install dependencies:
   pip install orchestral-ai pennylane torch torchvision python-dotenv
3. Copy .env.example to .env and add your DeepSeek API key
4. Run notebook.ipynb top to bottom

## Requirements
- Python 3.13+
- DeepSeek API key (free tier works): https://platform.deepseek.com

## Results (seed=42)
- Optimal LR: 0.1
- Best architecture by accuracy: 2L-circular-angle (31.84%)
- Best architecture by efficiency: 1L-linear-angle (ratio: 0.0313)
