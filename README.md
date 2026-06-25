# AI API Rate Limits: Real-World Comparison 2026

Compare rate limits, burst capacity, and 429 retry behavior across 12 AI API providers. With working code.

## Overview

We measured rate limits on 12 production AI APIs (OpenAI, Anthropic, DeepSeek, Qwen, GLM, Kimi, Mistral, Cohere, Google Gemini, AI21, Grok, Llama) over 30 days. This repo has the data, the test harness, and the visualization.

## How we measured

Each provider was probed with a controlled load test (10 req/sec sustained, 100 req/sec burst) for 5 minutes. We logged every 429, every retry-after, every rate-limit header.

## Results table

Per-provider: tier-1 free RPM, tier-1 paid RPM, burst allowance, retry-after behavior, error rate at 1.5x sustained. See rate-limits.csv.

## Code

Python + asyncio harness in `bench/` directory. Reproducible on your own keys.

## Why this matters

If you're building production AI features, rate limit handling is the difference between 'works on my machine' and 'works for 10,000 users'. See [aitoolreviewer.apiguider.com](https://aitoolreviewer.apiguider.com) for our related work on API evaluation.

---

Part of the apiguider.com network:
- Apex (editorial home): https://apex.apiguider.com
- All 22 stations: https://apex.apiguider.com/22-stations/
- Editorial standards: https://apex.apiguider.com/editorial-standards/

**Author**: apiguider.com editorial team (see apex.apiguider.com/about/)

Topics: ai-api, rate-limits, openai, anthropic, deepseek