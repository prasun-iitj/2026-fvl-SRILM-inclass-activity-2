# 2026 FVL — SRILM In-Class Activity 2

**Course:** 2026 Foundation of Vision & Language  
**Activity:** In-Class Activity 2  
**Topic:** SRILM-based n-gram language modelling

This repository keeps the notebook and report draft for the activity together so they can be updated as the work progresses.

## Files

- `M25AI2151_InClassActivity2.ipynb` — organized notebook, reflecting the work performed in Colab.
- `InClassActivity2_Report_Draft.pdf` — preliminary one-page report draft.
- `InClassActivity2_SRILM_Colab_Standalone.ipynb` — optional standalone copy for group members; it does not rely on the owner's Google Drive.

## Running the notebook

### Personal/organized notebook

The organized notebook expects the SRILM build and corpus files in the Google Drive folder it references. It documents the original compile-and-save workflow and subsequent reuse of that build.

### Standalone group notebook

1. Open the standalone notebook in Google Colab.
2. Run cells from top to bottom.
3. When asked, upload `brown-train.txt`, `brown-dev.txt`, and `brown-test.txt` from the course materials.
4. Wait for SRILM to compile, then allow the experiments to finish.
5. Download the generated ZIP containing logs and model artefacts.

A fresh Colab runtime must compile SRILM, which may take a while. The standalone notebook has not been verified through a complete fresh-runtime run.

## Experiments covered

- Word-sequence/bigram counts and unsmoothed bigram model
- Unknown-word handling using `-unk`
- Kneser–Ney bigram and trigram language models
- Punctuation removal and stopword-removal preprocessing
- Unigram/bigram interpolation tuned on the development set
- Add-smoothing and interpolation-weight grid search
- Test-set perplexity evaluation

## Important

The report is a draft. Verify the recorded outputs, including preprocessing metrics, against the generated logs before treating the report as final. Use the course's instructions for the submission requirements.
