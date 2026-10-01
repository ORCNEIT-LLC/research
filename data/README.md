# Numerical appendices / Числовые приложения

These are reported aggregate measurements, not independently reproduced experiments. CSV decimal separators are periods. Source texts, prompts and model weights are not part of these appendices. Methods, dates and limitations are in the corresponding RU/EN papers.

Это итоговые измерения описанных экспериментов, не независимое повторение. Десятичный разделитель CSV — точка. Условия, даты и ограничения приведены в статьях на русском и английском.

| File | Units and interpretation |
| --- | --- |
| project-milestones.csv | Dates and separate milestones; not one comparable evaluation series. Blank denominators are not applicable. The corpus row is a target only. |
| memory-instruction.csv | Correct general instruction responses out of 25, not memory task success. |
| memory-protocol.csv | Final repaired evaluation: 246 cases. Proposal/confirmation has 56 cases and 72 turns; do not add turns to the case denominator. Parsed format is not task success. |
| memory-learning.csv | Development loss by epoch; final held-out loss is a distinct 40-record set. |
| update-rounding.csv | Absolute mean signed update-writeback error on the first step. Not mean absolute per-weight error. The graph compares nearest and stochastic at unchanged update arithmetic; legacy_nearest is a separate arithmetic control. |
| numerical-stability.csv | A separate August run, not the July rounding comparison. Token exposures include repeated exposure; quality gate failed despite no nonfinite values. |
| tokenization-proxy.csv | Byte-normalized prediction scores. Equal source text, unequal tokens and steps; one seed. Practical tie threshold: 0.003, not a confidence interval. |
| response-control.csv | 400 prompts: one greedy and three sampling modes. Total 1,600 related outputs, not independent tasks. Paired transitions and termination reasons are separate partitions. |
| early-system-evaluation.csv | June system comparison on 79 cases. Rules sometimes bypassed the model; not an improvement in model weights. |
| training-observations.csv | Seventeen actual observations: training loss averaged over 250 steps, development loss on 8,192 tokens. |
| dialogue-observations.csv | Each model: 128 tasks × two modes = 256 responses. Different metrics are not parts of one total. |
| tokenizer-comparison.csv | August vocabulary comparison, distinct from July proxy training. Tokens per byte averaged equally across four text groups. |

No CSV value represents an independently validated ready assistant. See each paper for its explicit limitations.
