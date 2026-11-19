# Results: 229 vLLM Token-Generation Benchmark

**Main goal:** Measure vLLM token generation rate  
**Tools:** Start python -m vllm.entrypoints.openai.api_server on port 8000, then run scripts/benchmark_serving.py

Reference results measured by the maintainer on the system shown in each section (generator TEMPLATE_00_148 · recorded 2026-11-19). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× NVIDIA H100 NVL (95830 MiB) · AMD EPYC 9374F 32-Core Processor · Ubuntu 24.04.5 LTS · kernel 6.8.0-138-generic · driver 595.112.07
- **Run:** 2026-11-19T15:49:09Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 03:16 · benchmark 00:01 · whole run 03:30
- **Source:** run 229_20261119_154909
- **Command:** `bash run_benchmark.sh --smoke --model-name mistralai/Mistral-7B-v0.3 --dtype bfloat16 --tensor-parallel-size 1 --gpu-memory-utilization 0.9 --input-len 64 --output-len 16 --max-num-seqs 2 --max-concurrency 2`

| # | Metric | Result |
|---|---|---|
| 1 | Generated token rate (output_token_throughput_tokens_sec) | 295.2097604317742 |
| 2 | TPOT, ms (time_per_output_token_tpot_p50_msec) | 5.70667433203198 |
| 3 | Time To First Token, ms (ttft_p50_msec) | 15.867320005781949 |
| 4 | ITL, ms (inter_token_latency_itl_p50_msec) | 5.74237501132302 |
| 5 | End-to-end request latency p50, ms (end_to_end_request_latency_msec) | 102.19082797993906 |
<!-- /profile:smoke -->
