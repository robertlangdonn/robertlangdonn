### Prasad Khake

I'm an inference-systems engineer: I turn efficiency papers and tuning folklore into **measured, reproducible truth** — on hardware from a 16 GB MacBook to rented datacenter GPUs. The recurring question in my work: **what actually limits LLM inference, and how do those limits change across scales?**

**KV Cache Reality Lab** — [kv-cache-tax](https://github.com/robertlangdonn/kv-cache-tax): one model, one harness, cross-hardware (M3 vs rented NVIDIA L4), four measured legs:
- [The KV-cache tax](https://prasadkhake.com/blog/kv-cache-tax-m3-vs-l4) — what long context costs; includes a proven thermal-throttle finding on fanless Apple Silicon.
- [The eviction tax](https://prasadkhake.com/blog/kv-cache-eviction-tax) — a rotating KV window saves 36% of memory and collapses recall 5/5→0/5 the moment context crosses the window.
- [KV quantization: 4× slower on my Mac, 28% faster on an L4](https://prasadkhake.com/blog/kv-quantization-m3-vs-l4) — the same knob, opposite results; whether it helps is a property of the implementation × hardware pair, not the technique.
- Every number measured, medians of interleaved passes, raw data and rental runbooks in the repo.

**Inference cost engineering**
- [A measured audit of Llama-3.1-8B on a rented L4](https://prasadkhake.com/blog/inference-audit-8b-rag): FP8 cuts cost from $1.00 to $0.36 per million output tokens; everything else I tested — including the tuning-guide favorites — added nothing on top.

**Open source** (as robertlangdonn)
- [mlx-lm](https://github.com/ml-explore/mlx-lm): merged [#1349](https://github.com/ml-explore/mlx-lm/pull/1349) (Gemma 4 unified checkpoint loading); [#1329](https://github.com/ml-explore/mlx-lm/pull/1329) approved (tekken-v13 detokenizer root-cause, [writeup](https://prasadkhake.com/blog/mlx-tekken-detokenizer)); five more model-correctness PRs in review.
- [vLLM #49050](https://github.com/vllm-project/vllm/pull/49050) (in review): measured FP8-KV-cache performance documentation, backed by the Reality Lab data.
- [llm-compressor #2938](https://github.com/vllm-project/llm-compressor/pull/2938) (in review): Cohere2MoE + DeepseekV2 quantization mappings.
- [vllm-metal #382](https://github.com/vllm-project/vllm-metal/pull/382) (merged).

**From scratch, honestly benchmarked**
- [mlx-metal-kernels](https://github.com/robertlangdonn/mlx-metal-kernels) — GPU kernels for LLM inference written from scratch in Metal on an M3; five verified rungs.
- [ondevice-bench](https://github.com/robertlangdonn/ondevice-bench) — execution-checked local-LLM benchmarks (no rubric scoring), including [three bugs in my own benchmark](https://prasadkhake.com/blog/benchmark-bugs-that-inflated-my-scores).
- [lora-toolcalls](https://github.com/robertlangdonn/lora-toolcalls) — LoRA tool-calling fine-tune on a MacBook, with the adapter's inference cost measured, not assumed.

Professionally: production LLM pipelines (output quality gates, hallucination catching, webhook-driven retries with idempotency) and end-to-end automation architecture. Before that: [paperd.ink](https://www.paperd.ink), an open-source ESP32 e-paper board in makers' hands across 20+ countries, and [vcfkit](https://vcfkit.dev), a Rust genomics CLI 4× faster than bcftools.

Writing at **[prasadkhake.com](https://prasadkhake.com)** · **[On Device](https://ondevice.substack.com)**

📫 prasadkhake@gmail.com · [LinkedIn](https://linkedin.com/in/prasadkhake)
