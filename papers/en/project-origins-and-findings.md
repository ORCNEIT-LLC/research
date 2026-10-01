# ORCNEITGPT: how the project began and where it stands

From the first experiments with our own language model to a revised training approach and a new corpus. What we tested, which approaches fell short, and why the direction changed.

Observation period: 2026-06-13 — 2026-09-30.  
Published: 2026-10-01.

## Research question

How did the approach to ORCNEITGPT change after working prototypes, broader evaluations and unsuccessful attempts to improve the model?

## Methods

This account covers documented work from 13 June through 30 September 2026. Dates refer to experiments and decisions, not article publication. Early project work preceded company registration. This is a results overview, not a ledger of every development change.

We distinguish the language model, external response-control rules and the measurement instrument. Scores from different models, tasks and decoding modes cannot be combined into a single progress curve.

The values below were checked against preserved experimental results. Separate papers provide methods, tables and numerical supplements for individual questions. This overview connects those findings and decisions without replacing their limitations.

New-corpus status is based on the latest completed September records. Unfinished processing is not an accepted dataset. A target volume is not represented as ready data or completed training.

## Results

The project moved from a small prototype to its own training and stricter evaluation. A ready conversational model has not yet been obtained.

| Measure | Observation | Interpretation |
| --- | --- | --- |
| Project work began | 13 June 2026 | Own text processing, training and generation |
| Early expanded evaluation | 29 / 79 → 72 / 79 | Model → rule-controlled system; not improved weights |
| Final memory-learning evaluation | 0 / 246 tasks | After repairing multiline answer extraction |
| Bounded rounding test | 7.76 × 10⁻⁸ → 8.58 × 10⁻¹⁰ | Absolute mean signed update-writeback error |
| Completed August base training | 80,000 steps; 327,680,000 token exposures | Quality gate failed |
| Dialogue fine-tuning | 0 → 43 correct responses out of 256 | Improvement, but acceptance criteria unmet |
| New large corpus | Preparation continues | 4 billion tokens is a target, not accepted volume |

## Numerical appendices

- [project-milestones.csv](../../data/project-milestones.csv)

## Discussion

June: the project began with a small self-written core. Text representation, next-token training, generation and an interaction interface were implemented. Initial tests established that the pipeline worked, not broad knowledge or reliable performance on unfamiliar instructions.

Broader evaluation changed the picture: the early model passed 29 of 79 tasks; the rule-controlled system passed 72. In some scenarios rules replaced the model call with a prepared response. A good interface response therefore cannot automatically be attributed to the neural model. Later, external safeguards were measured separately while preserving the raw model's score.

Memory was the next question. A separate store could confirm, delete and supply records, but that did not establish model-level selection and mutation-protocol skills. Three fine-tuning attempts exposed forgetting and the partial benefit of replay. The final correctly measured test passed none of 246 memory tasks. This required reassessment, not a ready-memory claim.

In late June, a self-written billion-scale architecture was tested, followed by larger training experiments. Scale alone did not resolve the problems. July work examined small updates lost to rounding and compared tokenization through proxy training on identical source text, rather than compression alone.

August: continued training of an earlier model barely changed aggregate generation results: 497 versus 499 severely degenerate responses out of 1,600. Short controlled interventions did not produce an accepted repair. We chose to re-examine data and text processing and train the next model from fresh random initialization.

Base training completed on 22–23 August after 80,000 steps. Separate evaluation yielded 161 correct responses out of 640 against a required minimum of 167, while exceeding the allowed regression count. Dialogue fine-tuning improved termination and reduced repetition but solved only 43 of 256 responses. Both are published as completed experiments, not a ready-assistant release.

September: attention shifted to more varied data. Sources are checked for content and provenance, duplicates and overlap with evaluation sets. Final acceptance of the large corpus was not complete at September's end. Subsequent training must use accepted data and predefined quality criteria; this overview promises no model-release date.

## Limitations

- This is a retrospective of our own experiments, not independent certification or comparison with leading commercial models. Successful training execution and lower loss do not establish product readiness.
- Early, later and dialogue evaluations use different samples and definitions. They are not the same test. Their corresponding studies provide details and caveats.
- The overview does not claim that every method is a new scientific discovery. It reports measured project findings, including negative results, and reasons for decisions. Work after 30 September is outside this status snapshot.

[ORCNEIT Lab Research](https://orcneitlab.com/en-US/research)

© 2026 ORCNEIT LLC. All rights reserved.
