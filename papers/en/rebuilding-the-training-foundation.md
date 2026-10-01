# Why we are rebuilding the training corpus

Failed model evaluations prompted us to revisit the data, tokenization and evaluation itself. We report measured changes and the preparation of a new corpus, still in progress as of 26 September 2026.

Observation dates: 2026-08-20 — 2026-09-26.  
First published on LAB: 2026-09-26.  
GitHub edition prepared: 2026-10-01.

Status: in progress **as of 26 September 2026**.

## Research question

When additional training barely improves responses, should we continue the same model or re-examine the foundation it is learning from?

## Method

On 20 August, we decided against continuing one of our earlier models. Another 353.8 million token exposures had not improved free generation overall: severe degeneration moved from 497 to 499 out of 1,600 responses under the same evaluation. A control continuation and two separate training interventions also failed to produce an accepted repair. This decision concerned a particular model; verified tools and experimental evidence were retained.

The next model used fresh initialization and a newly verified text-processing pipeline. We tested the tokenizer, which turns text into model input units, for exact reconstruction, Unicode integrity and preservation of code and line breaks. Three vocabulary sizes were then compared on the same held-out sample. The chart labels identify variants in that comparison, not successive product releases.

The comparison metric is tokens per UTF-8 byte, averaged with equal weight across Russian, English, technical text and code. For the same text, lower values mean a more compact representation. All three variants passed integrity checks. Among variants within 3% of the best result, we selected the smaller vocabulary.

We also redesigned model evaluation. Verifiable tasks, context use and code-structure checks supplemented repetition diagnostics. Multiple-choice scoring initially favoured options with different token lengths. We kept full answer options in the prompt but scored single-token labels instead. All 2,816 scored continuations then had the same length.

Evaluation optimizations were accepted only when they matched reference computation. A fixed test compared token IDs, decoded text and response-termination state. We separately tested recovery after forced interruption: final files were byte-for-byte identical to an uninterrupted run.

The base-training and dialogue fine-tuning experiments described in the other two papers finished on 23 August. Both failed their quality gates. We then chose to prepare a substantially larger and more varied corpus instead of repeatedly fine-tuning the same weights. The target is 4 billion training tokens, plus separate evaluation samples. This is a planned volume, not a count of ready data.


## Results

Tokenization and evaluation gained measurable improvements. The new large corpus has not yet been accepted; preparation continues.

![Measured observations](../../figures/tokenizer.svg)

| Measure | Observation | Interpretation |
| --- | --- | --- |
| Vocabulary comparison on one sample | 0.365322 → 0.354379 → 0.348899 | Tokens per byte; the middle variant was selected |
| Selected vocabulary cost | 25% fewer embedding-matrix parameters | Versus the largest variant at equal width, not the entire model |
| Full tokenization check of the then-prepared dataset | 262,265 / 262,265 records | 0 reconstruction failures and 0 introduced replacement characters |
| Scored answer-length gap | Up to 17 tokens → 0 | Corrected scoring bias, not model errors |
| Evaluation-engine test run | 16.9655 → 4.6099 s | 512 generated tokens; identical output |
| New corpus preparation on 26 September 2026 | In progress | Exact and near-duplicate checks running; no final acceptance |

[Download chart data (CSV)](../../data/tokenizer-comparison.csv)

## Discussion

The largest vocabulary produced the most compact representation. The selected middle variant was about 1.57% behind it but needed one quarter fewer embedding-matrix parameters. This is a measured trade-off between compactness and cost, not a claim of an equivalent gain in model intelligence.

Full-dataset validation exposed something the small sample had missed: three rare characters in held-out data needed byte fallback. The fallback was lossless, but did not meet the required coverage rule. Those characters were added to the alphabet without using held-out texts or their frequencies to learn merges. Repeated full tokenization passed reconstruction checks on all 262,265 records.

The new evaluator asks more substantive questions of the model: task correctness, not just the absence of repetition. Before model evaluation, the tasks were checked against the actual training streams. The specified procedures found no exact matches or near copies. This is the result of a particular check, not a guarantee against every possible form of leakage.

The engineering test made evaluation about 3.68 times faster without changing its output. Faster alternatives were rejected: one changed 15 of 16 tested continuations, another changed 6 of 8. Computing a different result faster is not acceptable for model comparison.

Current work focuses on preparing data. Acquiring a source does not make it training-ready: its content, provenance, duplicates and overlap between training and evaluation splits must be checked. Exact and near-duplicate processing was running on 26 September. Final contamination checks and corpus acceptance are still ahead; model training on the new large corpus has not begun.


## Limitations

- Vocabulary comparison used a single fixed sample in August. It does not establish the same ratios on the future corpus. The tokenizer must be checked on the new data before use.
- The evaluation speed test used randomly initialized weights, 512 tokens and one compute setup. It measures evaluation mechanics, not trained-model quality, and does not promise a constant speedup.
- The earlier model and later experiments used different evaluation protocols. Their counts cannot be combined into one quality curve. Better tools alone do not establish model acceptance.
- Four billion tokens is a target. We do not claim that this volume has already been collected, cleaned or used for training. Status is recorded as of 26 September 2026; a completion date has not been set.

[Original publication](https://orcneitlab.com/en-US/research/rebuilding-the-training-foundation)

© 2026 ORCNEIT LLC. All rights reserved.
