# 06. Архитектура LLM I: порядок токенов и устройство блока

**Что разбираем.** Перестановочная эквивариантность self-attention без позиционной информации и масок. Что меняют causal mask и позиционные представления. Sinusoidal embeddings, RoPE, NoPE; перенос на большие длины. Residual connections, RMSNorm, SwiGLU. Какие задачи решают изменения внутри Transformer block.

## Материалы

[Слайды (pdf)](llm_architecture_1_slides.pdf) · [pptx](llm_architecture_1_slides.pptx)

* От текста до работающего decoder: токены и embeddings, self-attention и порядок, sinusoidal и RoPE, encoder vs decoder, современный блок (residual, RMSNorm, SwiGLU, multi-head), обучение и генерация маленькой языковой модели:
  [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Dustin-RS/LLM_MIPT_fall_2026/blob/mipt_26f/lesson06_llm_architecture_1/llm_architecture_1.ipynb)

Работает на CPU, нужны только `torch`, `numpy`, `matplotlib`. Все данные создаются внутри ноутбука.

## Дополнительное чтение

1. Andrej Karpathy, *Let's build GPT*, код: https://github.com/karpathy/ng-video-lecture
2. Attention Is All You Need: https://arxiv.org/abs/1706.03762
3. BERT: https://arxiv.org/abs/1810.04805
4. BPE для подслов: https://arxiv.org/abs/1508.07909
5. RoFormer / RoPE: https://arxiv.org/abs/2104.09864
6. The Impact of Positional Encoding on Length Generalization: https://arxiv.org/abs/2305.19466
7. RMSNorm: https://arxiv.org/abs/1910.07467
8. GLU Variants Improve Transformer (SwiGLU): https://arxiv.org/abs/2002.05202
9. PyTorch scaled_dot_product_attention: https://docs.pytorch.org/docs/stable/generated/torch.nn.functional.scaled_dot_product_attention.html
