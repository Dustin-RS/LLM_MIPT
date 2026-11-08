# 05. Evals: как понять, что система стала лучше

**Что разбираем.** Golden/private sets, executable graders, LLM-as-judge. Вариативность результатов, доверительные интервалы, pass@k и pass^k. Contamination, влияние промпта и scaffold на результат. Как читать лидерборды и сравнивать решения в одинаковых условиях. Arena, Artificial Analysis, BFCL, τ-bench, SWE-bench и OSWorld — примеры разных подходов к оценке.

## Материалы

* Evals для RAG и агентных систем на MuSiQue: базовый RAG → улучшения (RRF, HyDE, multi-query, агентный поиск) → метрики retrieval и ответа → локализация ошибок → абляции:
  [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Dustin-RS/LLM_MIPT_fall_2026/blob/mipt_26f/lesson05_evals/rag_evals_musique.ipynb)

**Запуск.** Ноутбук ожидает рядом с собой папку `data/` с файлами `musique_corpus.jsonl`, `musique_dev15.jsonl` и `source_support_audit.jsonl`. По умолчанию `RAG_MODE=live`: нужны реальные embeddings и LLM через [Polza.ai](https://polza.ai/docs/gaidy/chat-completions), ключ — в `POLZA_API_KEY`. `RAG_MODE=offline` прогоняет весь пайплайн без API: вместо embeddings — TF-IDF, вместо LLM — простые эвристики. Этот режим проверяет код, а не качество модели.

## Лидерборды и бенчмарки

* [Artificial Analysis](https://artificialanalysis.ai/) — качество, скорость и цена моделей в одинаковых условиях
* [Arena](https://arena.ai/leaderboard) — попарные сравнения ответов людьми
* [BFCL](https://gorilla.cs.berkeley.edu/leaderboard.html) — вызов функций (function calling)
* [τ-bench](https://github.com/sierra-research/tau-bench) — агенты в диалоге с пользователем и инструментами
* [SWE-bench](https://www.swebench.com/) — исправление реальных issue в репозиториях
* [OSWorld](https://os-world.github.io/) — агенты в настоящей операционной системе
* [Terminal-Bench](https://www.tbench.ai/), [DeepSWE](https://deepswe.datacurve.ai/)

## Дополнительное чтение

1. MuSiQue: данные, описание, лицензия CC BY 4.0: https://github.com/StonyBrookNLP/musique
2. Reciprocal Rank Fusion: https://research.google/pubs/reciprocal-rank-fusion-outperforms-condorcet-and-individual-rank-learning-methods/
3. HyDE: https://arxiv.org/abs/2212.10496
4. Оценка ранжированной выдачи, учебник Stanford IR: https://nlp.stanford.edu/IR-book/html/htmledition/evaluation-of-ranked-retrieval-results-1.html
5. RAGAS: https://arxiv.org/abs/2309.15217, ARES: https://arxiv.org/abs/2311.09476
6. Lost in the Middle: https://arxiv.org/abs/2307.03172
7. Contextual Retrieval, Anthropic: https://www.anthropic.com/engineering/contextual-retrieval
8. Retrieve & Re-Rank, Sentence Transformers: https://sbert.net/examples/sentence_transformer/applications/retrieve_rerank/README.html
9. Self-RAG: https://arxiv.org/abs/2310.11511, CRAG: https://arxiv.org/abs/2401.15884
