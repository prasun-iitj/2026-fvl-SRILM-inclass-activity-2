# Recorded experiment results

Course: **2026 Foundation of Vision & Language**  
Activity: **In-Class Activity 2 — SRILM**

This file summarizes values recorded in the current notebook and the experiment notes available during repository preparation. It is a compact guide to the outputs, not a replacement for the full executable notebook.

## Main model experiments

| Experiment | Recorded result |
|---|---|
| Model construction | Bigram counts, unsmoothed bigram, Kneser–Ney bigram, Kneser–Ney trigram, and unigram/bigram interpolation models built successfully in the recorded run. |
| Earlier unsmoothed-bigram evaluation without passing `-unk` to evaluation | 14,334 sentences; 305,056 words; 18,639 OOVs; 93,612 zero-probability events; log probability = -382,588.3; PPL = 70.30925; PPL1 = 96.45567. |
| Recorded Kneser–Ney trigram evaluation with `-unk` | 14,334 sentences; 305,056 words; 0 OOVs; 0 zero probabilities; log probability = -808,603.7; PPL = 340.1831; PPL1 = 447.3764. |
| Earlier default-smoothed bigram evaluation | 14,334 sentences; 305,056 words; 0 OOVs; 0 zero probabilities; log probability = -896,770.6; PPL = 642.3334; PPL1 = 870.3458. |

**Comparison caution:** the unsmoothed-bigram value above was recorded without explicitly enabling `-unk` during evaluation, while the trigram value was recorded with `-unk`. Do not treat those evaluations as a fully controlled comparison.

## Unigram/bigram interpolation: first tuning run

The mixture weights were tested on the development set. The best among the tested weights was `lambda = 0.1`, with development PPL1 = **427.8440**.

| Lambda | Development PPL1 |
|---:|---:|
| 0.1 | 427.8440 |
| 0.2 | 434.6117 |
| 0.3 | 446.6367 |
| 0.4 | 464.2692 |
| 0.5 | 488.8415 |
| 0.6 | 522.9922 |
| 0.7 | 571.9004 |
| 0.8 | 647.0939 |
| 0.9 | 782.7431 |

Test evaluation for the selected weight: 14,334 sentences; 305,056 words; 0 OOVs; 0 zero probabilities; log probability = -812,593.4; PPL = **350.1098**; PPL1 = **461.0538**.

## Add-smoothing and interpolation grid

The recorded grid tested add-smoothing values `0.01, 0.1, 0.5, 1.0` and lambda values `0.1, 0.3, 0.5, 0.7, 0.9`. The best setting *among those tested* was add-smoothing = **0.01** and lambda = **0.3**, with development PPL1 = **879.5534**.

| Add-smoothing | Lambda | Development PPL1 |
|---:|---:|---:|
| 0.01 | 0.1 | 909.3159 |
| 0.01 | 0.3 | 879.5534 |
| 0.01 | 0.5 | 913.8142 |
| 0.01 | 0.7 | 1010.1660 |
| 0.01 | 0.9 | 1254.9320 |
| 0.1 | 0.1 | 1228.0970 |
| 0.1 | 0.3 | 1136.0690 |
| 0.1 | 0.5 | 1139.3710 |
| 0.1 | 0.7 | 1208.4570 |
| 0.1 | 0.9 | 1399.7910 |
| 0.5 | 0.1 | 1725.1670 |
| 0.5 | 0.3 | 1483.4230 |
| 0.5 | 0.5 | 1420.9910 |
| 0.5 | 0.7 | 1437.4650 |
| 0.5 | 0.9 | 1550.3190 |
| 1.0 | 0.1 | 2031.3330 |
| 1.0 | 0.3 | 1677.8420 |
| 1.0 | 0.5 | 1565.6360 |
| 1.0 | 0.7 | 1543.6700 |
| 1.0 | 0.9 | 1607.2580 |

Test evaluation for the selected grid setting: 14,334 sentences; 305,056 words; 0 OOVs; 0 zero probabilities; log probability = -920,112.8; PPL = **760.0535**; PPL1 = **1038.029**.

These two interpolation experiments used different model/smoothing configurations. Their perplexities should not be compared as though they were one controlled experiment. The selected configuration is the minimum within the stated grid, not necessarily a global optimum.

## Preprocessing results

The notebook ran two test-set preprocessing variants:
1. Punctuation removal.
2. Punctuation removal plus English stopword removal.

The recorded notebook output confirms that both variants completed and that their evaluation output was saved to `preprocessing-results.txt` in the notebook owner's Drive. Numerical values for these two variants were not available in the inspected notebook output at the time this document was written, so they are not reproduced here. Rerun the preprocessing cell and copy the exact outputs into this section when available.
