# RAG Assignment: Baseline Retrieval vs Cross-Encoder Re-Ranking

Compares two retrieval pipelines over the same chunks of the EU AI Act (Regulation (EU) 2024/1689).

- **Pipeline 1:** all-MiniLM-L6-v2 bi-encoder + FAISS (cosine) -> Top 10 -> Top 3 -> Gemini -> Answer 1
- **Pipeline 2:** same Top 10 -> cross-encoder/ms-marco-MiniLM-L-6-v2 -> Top 3 -> Gemini (same prompt) -> Answer 2
- Failure analysis (keyword trap, exceptions, negation, buried chunk), rank shifts, latency, scaling estimate.

## Files
- `RAG.ipynb` - the full notebook with all outputs
- `report.pdf` - the 4-page analysis report

## How to run
1. Download the EU AI Act PDF from https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=OJ:L_202401689 and save it as `eu_ai_act.pdf` next to the notebook.
2. Open the notebook in Colab or Jupyter and run all cells.
3. Paste a Gemini API key when asked (https://aistudio.google.com/apikey). The key is never stored in the notebook.
