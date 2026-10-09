# 2026 FVL — SRILM In-Class Activity 2

**Course:** 2026 Foundation of Vision & Language  
**Activity:** In-Class Activity 2  
**Topic:** SRILM-based n-gram language modelling

This repository collects the notebooks, report draft, and supporting notes for the assignment. The files can be updated as experiments or results change.

## Files

- [`M25AI2151_InClassActivity2.ipynb`](M25AI2151_InClassActivity2.ipynb) — organized notebook reflecting the work performed in Colab, including the original compile-and-save workflow.
- [`InClassActivity2_SRILM_Colab_Standalone.ipynb`](InClassActivity2_SRILM_Colab_Standalone.ipynb) — standalone notebook for group members. It does not use the owner's Google Drive; it compiles SRILM in each fresh runtime and asks for the corpus files.
- [`InClassActivity2_Report_Draft.pdf`](InClassActivity2_Report_Draft.pdf) — preliminary one-page report draft.
- [`experiment-commands.txt`](experiment-commands.txt) — commands used for the main model experiments.
- [`docs/EXPERIMENT_RESULTS.md`](docs/EXPERIMENT_RESULTS.md) — summary of recorded results, tuning values, and comparison caveats.
- [`.gitignore`](.gitignore) — excludes local corpora, generated models, logs, and build artifacts from accidental commits.

## Run the standalone notebook

1. Open the standalone notebook from GitHub in Google Colab (use the download/raw option if prompted).
2. Run cells from top to bottom.
3. When prompted, upload `brown-train.txt`, `brown-dev.txt`, and `brown-test.txt` from the course-approved source.
4. Wait for SRILM to compile and then for the experiment cells to complete.
5. Download the generated ZIP of logs and model artifacts at the end.

A fresh Colab runtime compiles SRILM and may take a while. The standalone notebook has not been verified through a complete fresh-runtime run.

## Experiments covered

- Word-sequence/bigram counts and an unsmoothed bigram model
- Unknown-word handling using `-unk`
- Kneser–Ney bigram and trigram models
- Punctuation removal and stopword-removal preprocessing
- Unigram/bigram interpolation tuned on the development set
- Add-smoothing and interpolation-weight grid search
- Test-set perplexity evaluation

## Data and generated files

The corpus files, compiled SRILM archive, model binaries, and full generated logs are not committed. This keeps the repository focused and avoids redistributing course data without confirming permission. Get the required corpus split files from the course-approved source.

## Status and reproducibility

- The notebooks contain the experiment workflow; the saved result summary reflects outputs recorded during the earlier run.
- The exact preprocessing metrics should be copied from a current run's `preprocessing-results.txt` before the report is finalized.
- Results can differ if the corpus, SRILM build, preprocessing choices, or options change. The reported interpolation selection is only the best among the tested grid values, not a claim of global optimality.
- This repository is a working assignment archive. Check the course instructions before using any draft as a final submission.
