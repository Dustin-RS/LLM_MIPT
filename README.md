# LLM course

Курс girafe-ai по большим языковым моделям. МФТИ, осень 2026.

Как LLM превращает текст в следующий токен, как с ней работать через промпты и API, как строить и оценивать RAG-системы и почему современные архитектуры устроены именно так.

## Занятия и материалы

### Блок 1

| Дата | Занятие | Слайды | Ноутбуки | Комментарии |
|:----:|:--------|:------:|:---------|:------------|
| 09.09.2026 | [01. Как работает LLM: от текста до следующего токена](lesson01_how_llm_works) | | | Материалы будут добавлены |
| 18.09.2026 | [02. Промпты, reasoning и context engineering](lesson02_prompting_and_context) | | | Материалы будут добавлены |
| 23.09.2026 | [03. LLM на практике: локальный запуск и API](lesson03_llm_in_practice) | | | Материалы будут добавлены |
| 30.09.2026 | [04. RAG I: введение в retrieval-augmented generation](lesson04_rag#часть-1-введение-в-rag) | [Слайды](lesson04_rag/part1_intro/rag_intro_slides.pdf) | [Введение в RAG](lesson04_rag/part1_intro/rag_intro.ipynb) | |
| 07.10.2026 | [04. RAG II: компоненты и продвинутые техники](lesson04_rag#часть-2-компоненты-rag-и-продвинутые-техники) | [Слайды](lesson04_rag/part2_components/rag_part2_slides.pdf) | [Демо на паре](lesson04_rag/part2_components/rag_part2_demo.ipynb), [Компоненты RAG](lesson04_rag/part2_components/rag_components.ipynb), [Продвинутый RAG](lesson04_rag/part2_components/advanced_rag.ipynb) |  |
| 14.10.2026 | [05. Evals: как понять, что система стала лучше](lesson05_evals) | | [Evals для RAG · MuSiQue](lesson05_evals/rag_evals_musique.ipynb) | [Artificial Analysis](https://artificialanalysis.ai/) |

### Блок 2. Устройство и обучение современных LLM

Архитектурный блок строится от ограничений базового Transformer: порядок токенов, стоимость attention, масштабирование модели. Затем отдельно разбираем выполнение модели и её обучение.

| Дата | Занятие | Слайды | Ноутбуки | Комментарии |
|:----:|:--------|:------:|:---------|:------------|
| 21.10.2026 | [06. Архитектура LLM I: порядок токенов и устройство блока](lesson06_llm_architecture_1) | [Слайды](lesson06_llm_architecture_1/llm_architecture_1_slides.pdf) | [Собираем decoder с нуля](lesson06_llm_architecture_1/llm_architecture_1.ipynb) | |
| 28.10.2026 | [07. Архитектура LLM II: почему attention дорогой](lesson07_llm_architecture_2) | [Слайды](lesson07_llm_architecture_2/llm_architecture_2_slides.pdf) | [KV-cache, GQA, MLA, SSM](lesson07_llm_architecture_2/llm_architecture_2.ipynb) | |

Подробное описание каждого занятия, Colab-ссылки и материалы для дополнительного чтения — в README внутри папки занятия.

## Домашние задания

| № | Задание | Тема | Дедлайн |
|:-:|:--------|:-----|:-------:|
| 1 | [Доказательный RAG по ТФКП](homeworks/hw01_rag_tfkp) | RAG, retrieval, evals, отказы | см. объявление |

## Как запускать ноутбуки

Каждый ноутбук можно открыть в Google Colab по кнопке ![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg) в README занятия или запустить локально (Python 3.11, Jupyter / VS Code).

Ноутбукам, которые обращаются к LLM по API, нужен ключ. Ключи нигде в репозитории не хранятся: в Colab их добавляют через **Secrets** (значок ключа слева), локально — через переменные окружения.

| Занятие | Переменная | Сервис |
|:--------|:-----------|:-------|
| 04. RAG | `MISTRAL_API_KEY` | [Mistral AI](https://console.mistral.ai/) |
| 05. Evals | `POLZA_API_KEY` | [Polza.ai](https://polza.ai/) (OpenAI-совместимый API) |

Ноутбуки по архитектуре (06, 07) работают на CPU и не требуют ни GPU, ни ключей.

## Что нужно знать заранее

- Python, `numpy`, базовый `pandas`.
- Линейная алгебра: умножение матриц, скалярное произведение, нормы.
- Матанализ: производные, градиент.
- PyTorch: `torch.Tensor`, `nn.Module`, `backward`, цикл обучения.

## Структура репозитория

```
lessonNN_<тема>/      материалы занятия: README, ноутбуки, слайды (pdf + pptx)
homeworks/hwNN_<тема>/ условия домашних заданий и данные к ним
```

## Лицензия

Материалы курса распространяются по лицензии [MIT](LICENSE).

Сторонние материалы принадлежат своим авторам и распространяются на их условиях: примеры документов из репозитория [LangChain](https://github.com/langchain-ai/langchain) в `lesson04_rag/part2_components/`, датасет [MuSiQue](https://github.com/StonyBrookNLP/musique) (CC BY 4.0), учебник В. В. Горяйнова и Е. С. Половинкина «Лекции по ТФКП», по которому составлено ДЗ 1.

## Авторы курса

<!-- TODO: добавить преподавателей и контрибьюторов -->
* Омирзак Дастан
* Бородин Александр
* Нейчев Радослав
