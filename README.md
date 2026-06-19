### Prasad Khake

I make LLMs run well on real, constrained hardware — on-device, edge, Apple Silicon — and build the products around them.

The recurring question in my work: **what actually limits LLM inference on a machine you own, and how do those limits change as you scale?** Background: hardware (e-paper boards shipped to 20+ countries), Rust systems tooling, and AI-native full-stack development.

**On-device / inference (Apple's MLX)**
- Contributor to [mlx-lm](https://github.com/ml-explore/mlx-lm). Merged: [#1349](https://github.com/ml-explore/mlx-lm/pull/1349) — enables text-mode loading of Gemma 4 (`gemma4_unified`) checkpoints on MLX.
- [#1329](https://github.com/ml-explore/mlx-lm/pull/1329) (approved) — root-caused why Mistral/Devstral (tekken-v13) models emit `Ġ` instead of spaces on Apple Silicon, and fixed the detokenizer routing. [The writeup.](https://prasadkhake.com/blog/mlx-tekken-detokenizer)
- First merged contribution to [vLLM on Apple Silicon](https://github.com/vllm-project/vllm-metal) ([#382](https://github.com/vllm-project/vllm-metal/pull/382)).

**On Device — measuring the bottlenecks**
- [ondevice-bench](https://github.com/robertlangdonn/ondevice-bench) — an open-source, verifiable LLM benchmark that runs on the laptop in front of you, not a datacenter GPU. Code is executed and checked; no rubric scoring.
- Recent findings, measured on a 16 GB M3 MacBook Air:
  - [Turning a model's reasoning *off* makes Qwen3-4B beat Llama-3.1-8B](https://prasadkhake.com/blog/qwen3-4b-thinking-flag-16gb-mac) — at half the RAM.
  - [Gemma 4 12B: the multimodal tax](https://prasadkhake.com/blog/gemma-4-12b-m3-benchmark) — 11 GB and 2.7 tok/s for no text-quality gain.
  - [Three bugs in my own benchmark](https://prasadkhake.com/blog/benchmark-bugs-that-inflated-my-scores) — how a false fail looks exactly like a real one.

**Other work**
- [paperd.ink](https://www.paperd.ink) — open-source ESP32 e-paper dev board, in makers' hands across 20+ countries.
- [vcfkit](https://vcfkit.dev) — genomics CLI in Rust; 4× faster than bcftools, single static binary.
- [Hacker Newspaper](https://hackernews.paperd.ink) — comments-first mobile Hacker News reader.

Writing about on-device LLMs at **[prasadkhake.com](https://prasadkhake.com)** · **[On Device](https://ondevice.substack.com)**.

📫 prasadkhake@gmail.com · [LinkedIn](https://linkedin.com/in/prasadkhake)
