# RAG: Baseline Retrieval vs. Cross-Encoder Re-Ranking

Compares two retrieval pipelines over the MCC *Laws of Cricket*:

- **Pipeline 1 (baseline):** bi-encoder (`all-MiniLM-L6-v2`) + FAISS, top 10 by cosine similarity, top 3 sent to the LLM.
- **Pipeline 2 (re-ranking):** the same top 10, re-scored by a cross-encoder (`cross-encoder/ms-marco-MiniLM-L-6-v2`), top 3 sent to the LLM.

The LLM is Gemini (temperature 0), with the same prompt for both pipelines.

All code is in [`RAG_Baseline_vs_Reranking.ipynb`](RAG_Baseline_vs_Reranking.ipynb).

## How to run
1. Download the PDF: *The Laws of Cricket, 2017 Code, 4th Edition (2026)*, © Marylebone Cricket Club.
   It is available from MCC at https://www.lords.org/mcc/all-laws. Save it next to the notebook as
   `Laws-of-Cricket-2017-Code-4th-Edition-2026_COMPLETE.pdf`. The PDF is not included in this repo because MCC holds the copyright.
2. Install the dependencies: `pip install -r requirements.txt`
3. Copy `.env.example` to `.env` and add your Gemini API key.
4. Open the notebook and choose **Run All**.
