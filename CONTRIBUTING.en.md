# Contributing to ORCNEIT

[Русский](CONTRIBUTING.md) · [Code of conduct](CODE_OF_CONDUCT.en.md)

In `research`, these guidelines include a specific process for research publications. The [organization-wide guidelines](https://github.com/ORCNEIT-LLC/.github/blob/main/CONTRIBUTING.en.md) are also available in `.github`.

Contributing to ORCNEIT is not limited to programming. You can help clarify research reports, check numerical appendices, improve explanations, suggest ways to work with a future API, or create your own language materials through ORCNEIT Contributors. These activities use different contribution channels.

## What is available now

GitHub hosts [ORCNEITGPT research](https://github.com/ORCNEIT-LLC/research): Russian and English reports, figures and numerical appendices. You can report an error, ask about methods, suggest a translation improvement or propose a documentation correction. Publishing reports does not mean publishing the model's source code, weights or training data.

[ORCNEIT Contributors](https://contributions.orcneitlab.com) is a separate platform for creating and submitting language materials. Submit texts through that platform, not through GitHub Issues or pull requests.

Community participation in API development is a future direction. This document does not announce an available API or set a launch date. Public endpoints, capabilities, access rules and terms of use will be announced separately as they become ready.

## Developing an API with the community

We want ORCNEIT's future programming interface to reflect developers' real needs. Access to a model response is only part of that work. A clear contract also explains what a request accepts, what a response returns, how errors are handled and which limitations affect an integration.

### What can be discussed before an API opens

- **Integration needs.** Which product or workflow you want to connect to ORCNEIT, the result its users need and why the existing interaction is insufficient.
- **Request and response contracts.** Which data is actually necessary, how success differs from an error, and how limitations and compatibility changes should be explained.
- **Security and access control.** How to limit application permissions, avoid unnecessary data transfers and keep credentials out of examples and logs.
- **Testable interface quality.** Scenarios and tests that can expose ambiguous documentation or incorrect handling of cancellation, retries and service unavailability.

Describe the need and expected behavior without inventing endpoints, parameter names or guaranteed model capabilities. A feature request does not establish that the feature already exists.

### Participation after an interface is published

As individual components open, the community will be able to propose documentation improvements, integration examples, client libraries, adapters and compatibility checks within the scope actually published and permitted by each repository's terms.

Each component needs a clear purpose, supported versions, a way to verify changes and terms of use. Discuss substantial work with maintainers first: this helps agree on the task before building against a contract that has not been adopted.

The intended process is: describe the need → discuss the solution → agree on scope → implement with examples and tests → review → decide whether to include it. Public discussions and pull requests do not grant direct access to company production services.

We do not promise to open every component, set a schedule, accept every proposal or support compatibility with an unpublished API. ORCNEIT retains responsibility for release and maintenance decisions.

## ORCNEIT Contributors: contributing your own texts

A language model needs situations as well as words. The same phrase can express gratitude, irony or frustration; without context, that difference is easy to lose. Contributors helps collect independently created examples and human explanations of contemporary language.

### What you can create

- **Free-form texts:** stories, descriptions, explanations and other original materials.
- **Dialogues:** invented conversations with a sequence of turns and a clear situation. The author writes both sides; this is not a chat with a model.
- **Annotated texts:** explanations of expressions, abbreviations and language usage in context.
- **Task responses:** what an expression means, where and how it is used, and an example that explains it. Skip unfamiliar expressions rather than guessing.

Experience from different communities, professions and everyday situations matters because it is diverse. You do not need to imitate a universal dictionary: a specific, natural example and careful explanation matter more than length.

### How to participate

1. Open [Contributors](https://contributions.orcneitlab.com) and choose registration or sign-in.
2. Read the current documents and choose an original material or a task.
3. Write independently. Use invented situations instead of real private correspondence or personal details.
4. Check the content, authorship and absence of prohibited data; separately review the material and exclusive-right assignment agreement before submission.
5. Submit through the platform and check the acceptance confirmation. A draft or clicking a button alone does not establish a completed transfer.

Contributors participation is unpaid and open to adults aged 18 and over. Do not submit other people's works, personal data, passwords, access keys, confidential documents or automatically generated text in place of your own response. Do not move participants' materials onto GitHub.

Submission does not mean immediate use in training. Materials undergo the prescribed checks; not every text will be suitable for further use. We do not promise that a single submission will change the model's behavior or result in compensation.

The mandatory conditions and transfer process are defined by the [current Contributors documents](https://help.orcneit.com/ru-RU/articles/orcneit-contributors-texts), not this overview. GitHub guidelines do not replace those documents or complete a transfer through the platform.

Read more about its purpose and features: [“ORCNEIT Contributors: language begins with people”](https://orcneitlab.com/en-US/news/orcneit-contributors).

## Preparing a GitHub proposal

Read the relevant repository's README and existing discussions first. Russian and English are both welcome; proficiency in a particular language is not a condition for respectful participation.

For an issue, include:

- the publication, file or public component concerned;
- the problem, expected result and practical purpose of the change;
- a verifiable example, calculation or reproduction steps;
- known limitations and any source you rely on.

For a pull request, keep distinct tasks separate, explain your changes and provide the necessary checks. In research reports, preserve experiment dates, measurement conditions and the limitations of conclusions. Do not present a CSV arithmetic check as independently repeated training or replace published measurements with unsupported values.

If automated tools helped prepare code or documentation, review the result yourself and disclose substantial use in the change description. This does not waive the independent-authorship requirement for Contributors materials.

Every proposal is reviewed. Revisions may be needed; maintainers may decline changes that fall outside a repository's purpose, lack evidence or are not ready for publication. An issue or pull request does not guarantee acceptance or establish a response deadline.

## Contributing to research specifically

This repository contains reports and numerical appendices, not a working API. Do not add future-interface proposals to experimental-result CSVs or present them as implemented features. If an idea has no suitable public repository yet, use the cooperation contact below.

To correct a report:

1. Identify the paper, section, table row or figure and explain the discrepancy.
2. Provide a calculation using published data or a source supporting the correction. Do not attach someone else's unpublished data.
3. Distinguish a typo correction, a recalculated derived value and a changed scientific conclusion: they require different review evidence.
4. When a table or numerical appendix changes, check the related figures and explanations. Preserve units, denominators and comparison conditions; do not fill missing measurements with guesses.
5. Keep Russian and English versions consistent. If you can prepare only one, state that the other translation still needs review.
6. List affected materials, completed checks and remaining limitations in the pull request description.

New results are considered separately from corrections to existing work. Do not retroactively change observation dates or conceal negative results. Identify new independent research as a separate study, not as measurements performed by ORCNEIT.

## Rights, data and safe publication

Propose only material you are entitled to submit for review and publication. Identify the origin of borrowed material and comply with its conditions of use. Do not add a new license or claim the entire project is open: terms are defined separately for each published component. If a contribution requires a separate agreement, its terms must be communicated before that contribution is accepted.

Issues, pull requests and attachments must not contain active credentials, private correspondence, participant data, confidential training materials or details of protected systems. Use invented data in examples. Do not test a suspected bug on someone else's account or a production service without permission.

## Contact channels

- Proposals about published material: the relevant repository's Issues; for research, [ORCNEIT-LLC/research](https://github.com/ORCNEIT-LLC/research/issues).
- Contributors and account support: [support@orcneitlab.com](mailto:support@orcneitlab.com).
- Conduct violations and possible vulnerabilities: privately to [report@orcneitlab.com](mailto:report@orcneitlab.com), without active credentials or sensitive details in public Issues.
- Cooperation and proposals without a corresponding public repository: [contact@orcneitlab.com](mailto:contact@orcneitlab.com).

Read the [community code of conduct](CODE_OF_CONDUCT.en.md) before participating.
