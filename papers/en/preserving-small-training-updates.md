# Preserving small updates during training

A bounded numerical comparison reduced mean signed update-writeback error by about 90-fold. A separate later run established stable training with high-precision state, but not model readiness.

Observation period: 2026-07-07 — 2026-08-21.  
Published: 2026-10-01.

## Research question

What happens to small weight updates during rounding, and can systematic error be reduced without turning that finding into a model-quality claim?

## Methods

On 7 July we compared three paths from identical initial state: legacy arithmetic with round-to-nearest; higher-precision update arithmetic with the same rounding; and that second path with stochastic rounding only at weight writeback. Each branch was limited to 20 steps. Data order, initial weights and other comparison conditions were preserved.

BF16 has a limited spacing between representable weights. An update below half that spacing can round back to the previous value. Stochastic rounding selects a neighbouring representable number probabilistically to avoid systematically discarding small updates in one direction. We tested a particular implementation, not the scientific invention of the method.

The primary measure is the absolute mean signed difference between written and higher-precision intended updates on the first identical step of real tensors. This measures bias: large errors with opposite signs can cancel. It is not mean absolute per-weight error.

Additional synthetic tests examined small updates and preservation of the rounding random sequence. Continuous and interrupted execution were checked separately. Complete training was not bitwise reproducible; resumed differences were around the observed variability of repeated continuous runs.

A separate run completed on 21 August with 1,200 steps and 4,915,200 token exposures, retaining master weights and optimizer state in FP32 while using BF16 model computation. It used a different model and conditions, not a continuation of the July comparison. It establishes the operation of high-precision training state, not a causal comparison between methods.

## Results

Stochastic rounding reduced measured bias by about 90-fold in the bounded comparison. Improved responses were not established.

![Update writeback error](../../figures/preserving-small-training-updates-en.svg)

Lower is better. First-step measurement on identical real weights and gradients. Mean signed error, not mean absolute per-weight error or response quality.

| Measure | Observation | Interpretation |
| --- | --- | --- |
| Update arithmetic with nearest rounding | 7.76 × 10⁻⁸ | Absolute mean signed error |
| Same arithmetic with stochastic rounding | 8.58 × 10⁻¹⁰ | Only weight writeback changed |
| Ratio of the two errors | ≈ 90.44 | Not a 90-fold model-quality gain |
| Intended updates below half BF16 spacing | About 95% in sampled blocks; 99.7% in token representations | First step; not every weight at every step |
| Maximum synthetic rounding bias | 1.2 × 10⁻³ representable spacing | Separate rounding test |
| Later separate FP32-state run | 1,200 steps; NaN/Inf: 0 | Execution completed; behavioral gate failed |
| Severe later evaluation failures | 487 / 1,600 | Above the predefined 10% ceiling |

## Numerical appendices

- [update-rounding.csv](../../data/update-rounding.csv)
- [numerical-stability.csv](../../data/numerical-stability.csv)

## Discussion

Higher-precision intermediate arithmetic with unchanged weight writeback left bias near its previous level. Changing only rounding produced the difference. This localizes the numerical effect within the bounded controlled comparison.

Stochastic rounding need not change every weight on every step: many writes remain zero while small movements occur probabilistically. Lower mean bias does not eliminate all individual errors.

A causal connection to deteriorating long-form generation was not established. Data, training regime and decoding remain other possible contributors. The July probe did not evaluate response quality at all.

The separate August FP32-state run completed every update without nonfinite values. Yet 487 of 1,600 generations were severely degenerate and the quality gate failed. Numerical stability and learned capability remain distinct.

## Limitations

- The July comparison is short. The approximately 90-fold ratio applies to the stated first-step aggregate, not long training, speed, every weight error or text quality.
- The saved rounding random sequence was reproducible in synthetic tests; the full model showed computational variability. Bitwise-identical resumption of complete training cannot be claimed.
- The July comparison and August run have different goals, models and data. Their values cannot form one curve or establish superiority of one complete training recipe. Independent replication is not provided.

[ORCNEIT Lab Research](https://orcneitlab.com/en-US/research)

© 2026 ORCNEIT LLC. All rights reserved.
