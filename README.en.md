# ORCNEITGPT — research

[Русский](README.md)

Three engineering research reports from ORCNEIT Lab on the development of our language model, ORCNEITGPT. Each report includes the experiment conditions, measurements, conclusions and limitations. CSV tables and charts use the same observations.

ORCNEITGPT remains in research development. Completing training does not mean passing a quality gate or becoming ready for public use.

## Reports

| Report | Observation dates | Main result |
| --- | --- | --- |
| [Language-model training from scratch](papers/en/language-model-pretraining.md) | 22–23 August 2026 | 80,000 steps and 327.68 million token exposures; the combined quality gate failed |
| [Dialogue fine-tuning](papers/en/dialogue-fine-tuning.md) | 23 August 2026 | Correct responses increased from 0 to 43 out of 256; assistant acceptance criteria were not met |
| [Rebuilding the training foundation](papers/en/rebuilding-the-training-foundation.md) | 20 August–26 September 2026 | Measured tokenizer and evaluator changes; the new corpus was not yet accepted at the observation date |

## Interpretation

These are reports of ORCNEIT's own experiments, not comparisons with commercial models or independent assessments. Lower prediction loss, less repetition and faster evaluation measure different things. None alone establishes a ready assistant.

327.68 million tokens counts training exposure, including repeated passes, not unique corpus size. Dialogue evaluation produced 256 results from 128 tasks in two generation modes. Four billion tokens is a target, not a volume already collected or used for training.

## Data and charts

- [Training curve](figures/training.svg) · [CSV](data/training-observations.csv)
- [Dialogue fine-tuning comparison](figures/dialogue.svg) · [CSV](data/dialogue-observations.csv)
- [Tokenizer comparison](figures/tokenizer.svg) · [CSV](data/tokenizer-comparison.csv)

The reports were first published on the [laboratory website](https://orcneitlab.com/en-US/research) on 26 September 2026. This GitHub edition was prepared on 1 October 2026. Publication dates do not change experiment dates or the date of an observed project status.

## Contact

[ORCNEIT Lab](https://orcneitlab.com) · [Help Center](https://help.orcneitlab.com) · contact@orcneitlab.com

© 2026 ORCNEIT LLC. All rights reserved.
