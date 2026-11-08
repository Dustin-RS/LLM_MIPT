# 04. RAG и работа с внешними знаниями

**Что разбираем.** Embeddings, BM25, dense/hybrid search, chunking, reranking, query rewriting. Сборка базового RAG и раздельная оценка retrieval и генерации: recall/precision, groundedness, ссылки на источники. Long context vs RAG vs fine-tuning. Модульный RAG; HyDE, multi-query и GraphRAG — расширения.

Тема заняла две пары.

## Часть 1. Введение в RAG

[Слайды (pdf)](part1_intro/rag_intro_slides.pdf) · [pptx](part1_intro/rag_intro_slides.pptx)

* Введение в RAG: меры близости, sentence embeddings, векторный поиск и векторные БД, первый RAG-пайплайн на LangChain:
  [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Dustin-RS/LLM_MIPT_fall_2026/blob/mipt_26f/lesson04_rag/part1_intro/rag_intro.ipynb)

## Часть 2. Компоненты RAG и продвинутые техники

[Слайды (pdf)](part2_components/rag_part2_slides.pdf) · [pptx](part2_components/rag_part2_slides.pptx) · [Короткий тест](part2_components/rag_part2_quiz.md)

* Демонстрация на паре: документ и его происхождение, чанкинг и overlap, retriever, контекст с источниками, проверка поиска отдельно от ответа:
  [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Dustin-RS/LLM_MIPT_fall_2026/blob/mipt_26f/lesson04_rag/part2_components/rag_part2_demo.ipynb)
* Компоненты RAG: document loaders, text splitters, embedding-модели, vector stores, retrievers:
  [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Dustin-RS/LLM_MIPT_fall_2026/blob/mipt_26f/lesson04_rag/part2_components/rag_components.ipynb)
* Продвинутые техники: сжатие промптов, Corrective RAG, Self-RAG, Adaptive RAG:
  [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Dustin-RS/LLM_MIPT_fall_2026/blob/mipt_26f/lesson04_rag/part2_components/advanced_rag.ipynb)

Файлы `facebook_chat.json`, `fake-content.html`, `layout-parser-paper.pdf`, `mlb_teams_2012.csv` — примеры документов для загрузчиков. Ноутбук `rag_components.ipynb` при запуске сам скачивает их из репозитория LangChain, так что в Colab ничего загружать не нужно.

Для вызовов LLM нужен ключ `MISTRAL_API_KEY` (в Colab — через Secrets).

## Дополнительное чтение

1. BM25: Robertson & Zaragoza, *The Probabilistic Relevance Framework: BM25 and Beyond*: https://www.staff.city.ac.uk/~sbrp622/papers/foundations_bm25_review.pdf
2. MTEB — бенчмарк embedding-моделей: https://github.com/embeddings-benchmark/mteb
3. Encodechka — бенчмарк русскоязычных энкодеров: https://github.com/avidale/encodechka
4. Модель E5 (multilingual-e5-small): https://huggingface.co/intfloat/multilingual-e5-small
5. Corrective RAG (CRAG): https://arxiv.org/abs/2401.15884, реализация на LangGraph: https://langchain-ai.github.io/langgraph/tutorials/rag/langgraph_crag/
