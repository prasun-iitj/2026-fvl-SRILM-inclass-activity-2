# Activity coverage and final checks

The original activity handout is not copied into this public repository. This file summarizes the task areas in it and records the current notebook/report status so the group can check coverage.

## Activity task areas

| Handout task | Current notebook status | Before calling it complete |
|---|---|---|
| Generate bigram counts from the Brown training split | Included | Run the count cell and check the generated count file. |
| Train an unsmoothed model using `-addsmooth 0` and consider `-unk` | Included | Compare test evaluation with and without evaluation-time `-unk`; explain the zero-probability/OOV behavior in your own words. |
| Use another smoothing method and compare perplexity/OOV handling | Included using Kneser–Ney | Use consistent evaluation options when comparing results. |
| Train/test a trigram language model | Included using Kneser–Ney trigram | Keep the recorded test metrics and options in the report. |
| Compare punctuation removal and stopword removal | Included | Run the preprocessing cell and add the exact two sets of test metrics from `preprocessing-results.txt` to the report. |
| Tune interpolation weight and `-addsmooth` on development data, then evaluate the selected setting on test data | Included as two runs | Describe the two configurations separately; the first tuning run and add-smoothing grid used different model setups. |
| Estimate per-word probabilities / inspect `-debug 2` output | Not currently a dedicated notebook section | Add only if required by the instructor or the interpretation of the handout calls for it. |

## Wording note about interpolation

The handout's introductory sentence mentions a combination of bigram and trigram models, but its detailed substeps specifically ask for separate unigram and bigram language models combined using `-mix-lm`, with the interpolation weight and `-addsmooth` tuned on `brown-dev.txt`. The current notebook follows those detailed substeps (unigram + bigram). Confirm with the instructor if the intended model combination is unclear.

## Before finalizing the report

- [ ] Run the notebook in the intended environment and keep the run's exact outputs.
- [ ] Copy the numerical punctuation-only and punctuation-plus-stopword results from the preprocessing log.
- [ ] State the data split and command options used for each reported metric.
- [ ] Do not compare perplexity results directly where evaluation options or model configurations differ.
- [ ] Explain observations in your own words and follow the instructor's instructions for the submitted report and notebook.
