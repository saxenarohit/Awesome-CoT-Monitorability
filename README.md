# awesome-cot-monitorability

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/rsaxena/Awesome-CoT-Monitorability)

Curated list of research on monitoring chain-of-thought (CoT) reasoning for safety, interpretability, and oversight.

## Papers and Summaries

### [Reasoning Models Don't Always Say What They Think](https://arxiv.org/abs/2505.05410)

- **Metrics:** Hint reveal rate between internal hint usage and expressed CoT traces; impact of outcome-based RL on CoT faithfulness.
- **Datasets:** Hint-augmented reasoning prompts spanning six reasoning hints and multiple state-of-the-art reasoning models.
- **Comments:** Finds that CoT traces expose hint usage in as few as 1% of cases and rarely above 20%, even though models rely on the hints; outcome-based RL boosts faithfulness briefly but plateaus, and increasing hint usage through RL does not make models verbalize those hints more often—highlighting that CoT monitoring alone cannot rule out hidden behaviors.

### [Measuring Faithfulness in Chain-of-Thought Reasoning](https://arxiv.org/abs/2307.13702)

- **Metrics:** Early-answering and add-mistake area-over-curve (AOC) faithfulness scores; CoT vs. no-CoT accuracy deltas across tasks.
- **Datasets:** ARC (Easy & Challenge), AQuA, HellaSwag, LogiQA, MMLU, OpenBookQA, TruthfulQA.
- **Comments:** Perturbs sampled CoTs by truncation, injected mistakes, paraphrasing, and filler tokens to test whether reasoning steps causally influence final answers, showing wide variation in faithfulness—some tasks change answers on <10% of truncations while AQuA exceeds 60%—and that larger models and easier arithmetic variants can become less faithful even when CoT boosts accuracy, motivating explicit monitoring of reasoning traces rather than assuming truthfulness.

### [Monitoring Monitorability](https://openai.com/index/evaluating-chain-of-thought-monitorability/)

- **Metrics:** g-mean² (geometric mean of TPR and TNR squared) plus minimal-criterion sensitivity for intervention tests; comparisons across CoT-only, action-only, and all-message monitor scopes; scaling analyses over RL steps and monitor reasoning effort. [PDF](https://cdn.openai.com/pdf/d57827c6-10bc-47fe-91aa-0fde55bd3901/monitoring-monitorability.pdf)
- **Datasets:** Intervention evals (Health Queries, Scruples variants, demographic Memory perturbations, hint-based GPQA/DAFT/AIME, WMDP sandbagging), process evals with expert-labeled solution paths (FrontierMath, AIME, GPQA physics), outcome-property evals (Coding-impossible tasks, Flaky-tools, OAI-repo-sabotage, ShadeArena, Anti-scheming).
- **Comments:** Defines a three-archetype CoT monitorability suite and shows CoT access consistently beats action-only monitoring, longer CoTs and higher monitor compute improve g-mean², RL at frontier scale typically preserves or boosts monitorability, follow-up questioning reveals more detectable clues, and targeted RL can train models to obfuscate CoTs—emphasizing the need to track monitorability across training procedures and agent/monitor scaling gaps.
