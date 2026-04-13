# Learn CS336: Language Modeling from Scratch

Self-study notes and assignments for [Stanford CS336](https://cs336.stanford.edu/) (Spring 2026), with reference to [datawhalechina/diy-llm](https://github.com/datawhalechina/diy-llm).

## Structure

```
notes/          — Lecture notes per topic
prompts/        — Key AI prompts and responses during study
assignments/    — Assignment code
  a1_basics/    — Tokenizer, architecture, optimizer, training
  a2_systems/   — Profiling, FlashAttention2, distributed training
  a3_scaling/   — Transformer analysis, scaling laws
  a4_data/      — Common Crawl processing, filtering
  a5_alignment/ — SFT, reinforcement learning (GRPO)
experiments/    — Training logs, wandb screenshots, results
references/     — Papers, useful links
```

## Environment

- Python 3.11 (managed by uv)
- GPU: RTX 5060 Laptop 8GB (local debug) + cloud GPU (training)

## Setup

```bash
uv venv
source .venv/bin/activate
uv sync
```
