# 07. Архитектура LLM II: почему attention дорогой

**Что разбираем.** Стоимость вычислений и памяти при увеличении контекста. KV-cache, MQA/GQA, MLA, sparse и sliding-window attention. Различия между изменением архитектуры и оптимизацией реализации. Введение в SSM, Mamba-подобные и гибридные архитектуры как альтернативные способы работы с последовательностями.

## Материалы

[Слайды (pdf)](llm_architecture_2_slides.pdf) · [pptx](llm_architecture_2_slides.pptx)

* Стоимость attention, генерация и KV-cache, MQA/GQA/MLA, sliding window и sparse attention, архитектура vs реализация, линейное внимание, SSM и Mamba, разбор DeepSeek-V3 и Qwen3.8-Flash-Next:
  [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Dustin-RS/LLM_MIPT_fall_2026/blob/mipt_26f/lesson07_llm_architecture_2/llm_architecture_2.ipynb)

Работает на CPU, GPU и API-ключи не нужны.

## Дополнительное чтение

**Как уменьшить KV-cache**

1. MQA, *Fast Transformer Decoding*: https://arxiv.org/abs/1911.02150
2. GQA: https://arxiv.org/abs/2305.13245
3. DeepSeek-V2 (MLA): https://arxiv.org/abs/2405.04434
4. DeepSeek-V3 Technical Report: https://arxiv.org/abs/2412.19437

**Смотрим не на все токены**

5. Longformer: https://arxiv.org/abs/2004.05150
6. Mistral 7B (sliding window): https://arxiv.org/abs/2310.06825
7. StreamingLLM, attention sinks: https://arxiv.org/abs/2309.17453
8. Native Sparse Attention: https://arxiv.org/abs/2502.11089

**Оптимизация реализации**

9. FlashAttention: https://arxiv.org/abs/2205.14135
10. PagedAttention / vLLM: https://arxiv.org/abs/2309.06180

**Линейное внимание, SSM и гибриды**

11. Transformers are RNNs (линейное внимание): https://arxiv.org/abs/2006.16236
12. Mamba: https://arxiv.org/abs/2312.00752, Mamba-2: https://arxiv.org/abs/2405.21060
13. DeltaNet: https://arxiv.org/abs/2406.06484, Gated DeltaNet: https://arxiv.org/abs/2412.06464
14. Jamba: https://arxiv.org/abs/2403.19887
15. MiniMax-01: https://arxiv.org/abs/2501.08313
16. Qwen3-Next-80B-A3B: https://huggingface.co/Qwen/Qwen3-Next-80B-A3B-Thinking
17. Qwen3.8-Flash-Next: https://github.com/QwenLM/Qwen3.8-Flash-Next/, технический отчёт: https://arxiv.org/abs/2608.30320
