# awesome-cot-monitorability

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/rsaxena/Awesome-CoT-Monitorability)

Curated list of research on monitoring chain-of-thought (CoT) reasoning for safety, interpretability, and oversight.

## Papers and Summaries

### [Reasoning Models Don't Always Say What They Think](https://arxiv.org/abs/2505.05410)

- **Comments:** Finds that CoT traces expose hint usage in as few as 1% of cases and rarely above 20%, even though models rely on the hints; outcome-based RL boosts faithfulness briefly but plateaus, and increasing hint usage through RL does not make models verbalize those hints more often, highlighting that CoT monitoring alone cannot rule out hidden behaviors.

### [Chain of Thought Monitorability: A New and Fragile Opportunity for AI Safety](https://arxiv.org/abs/2507.11473)

- **Comments:** Argues that language-based reasoning offers a unique but delicate chance to detect misbehavior via CoT monitoring, surveys current evidence, highlights research gaps around evaluating necessity versus propensity to externalize reasoning, and warns that training choices such as process supervision, CoT penalties, or latent architectures could erode monitorability, urging frontier developers to consider these risks and invest in dedicated CoT monitoring research.

### [Measuring Chain-of-Thought Monitorability Through Faithfulness and Verbosity](https://arxiv.org/abs/2510.27378)

- **Comments:** Defines monitorability as the product of CoT faithfulness and verbosity, measures both on BBH, GPQA, and MMLU for instruction-tuned and reasoning models, and finds that models can look faithful while omitting critical factors and that monitorability differs sharply across model families, with Inspect-based evaluation code released for reproducibility.

### [Measuring Faithfulness in Chain-of-Thought Reasoning](https://arxiv.org/abs/2307.13702)

- **Comments:** Perturbs sampled CoTs by truncation, injected mistakes, paraphrasing, and filler tokens to test whether reasoning steps causally influence final answers, showing wide variation in faithfulness, noting that some tasks change answers on <10% of truncations while AQuA exceeds 60%, and that larger models and easier arithmetic variants can become less faithful even when CoT boosts accuracy, motivating explicit monitoring of reasoning traces rather than assuming truthfulness.

### [Monitoring Monitorability](https://openai.com/index/evaluating-chain-of-thought-monitorability/)

- **Comments:** Defines a three-archetype CoT monitorability suite and shows CoT access consistently beats action-only monitoring, longer CoTs and higher monitor compute improve g-mean², RL at frontier scale typically preserves or boosts monitorability, follow-up questioning reveals more detectable clues, and targeted RL can train models to obfuscate CoTs, emphasizing the need to track monitorability across training procedures and agent/monitor scaling gaps.
