# WHO Clinical Guidelines RAG Chatbot

A Retrieval-Augmented Generation (RAG) chatbot built over three World Health Organization (WHO) clinical guideline PDFs. The notebook explores how chunking, retrieval depth, clinical query expansion, and prompt design affect the quality and traceability of generated answers.

> **Important:** This is an educational RAG experiment, not a clinically validated medical system. It must not be used to make diagnosis or treatment decisions. Always consult the original WHO documents and qualified healthcare professionals.

## Notebook

[Open the Google Colab notebook](https://colab.research.google.com/drive/1ddNzy2ZydDJKKHXpsoepCxX5Oeu1UicF?usp=sharing)

## Knowledge Sources

The notebook processes these three WHO guideline PDFs:

1. **2012 — Prevention and Control of Noncommunicable Diseases:** primary-care guidance covering Type 2 Diabetes, Asthma, and COPD.
2. **2020 — HEARTS-D:** diagnosis and management of Type 2 Diabetes.
3. **2021 — Pharmacological Treatment of Hypertension in Adults.**

The PDF files are not included in this repository. Upload the source documents to the Colab session before running the notebook.

## Architecture

```text
WHO guideline PDFs
       |
       v
PDF text extraction (PyPDF)
       |
       v
Page-level text + source metadata
       |
       v
Chunking
       |
       v
PubMedBERT embeddings (Sentence Transformers)
       |
       v
ChromaDB vector store
       |
       v
Clinical query / query expansion
       |
       v
Top-k retrieval
       |
       v
Groq LLM (OpenAI-compatible SDK)
       |
       v
Grounded answer + source/page citations
       |
       v
LLM-as-a-Judge evaluation
```

## Technology Stack

- **Python / Google Colab** — notebook environment
- **PyPDF** — PDF text extraction with page-level metadata
- **Hugging Face Sentence Transformers** — `NeuML/pubmedbert-base-embeddings`
- **ChromaDB** — vector storage and similarity retrieval
- **LangChain Text Splitters** — fixed-character and recursive chunking
- **Groq API** — answer generation and evaluation through the OpenAI-compatible SDK
- **Pandas / Matplotlib** — evaluation summaries and visual comparison

## Implementation

### 1. Document ingestion

- Loads the three guideline PDFs page by page.
- Extracts text and retains the source filename and page number.
- Skips pages with very little extracted text.

### 2. Baseline RAG

The baseline uses:
- Fixed character chunking: 500 characters
- No chunk overlap
- PubMedBERT embeddings generated locally
- ChromaDB for vector storage
- Top-2 retrieval
- A context-grounded answer prompt

### 3. Evaluation

A six-question benchmark set covers clinical information from the source guidelines. An LLM-as-a-Judge evaluates generated answers on a 1–5 scale across:

- **Faithfulness** — whether the answer stays grounded in retrieved context
- **Relevance** — whether it addresses the question
- **Completeness** — whether it captures the key information in the reference answer

The notebook computes an overall score as the mean of these three dimensions.

### 4. Retrieval improvement experiments

| Experiment | Change | Retrieval configuration |
|---|---|---|
| Baseline | Fixed-character chunks | 500 characters, no overlap, top-k 2 |
| Experiment 1 | Recursive, structure-aware splitting | 1,000-character chunks, 200 overlap, top-k 4 |
| Experiment 2 | Clinical query expansion | Expanded clinical query, top-k 4 |
| Experiment 3 | Combined original + expanded query and clinical system prompt | top-k 5, inline source/page citations |

Experiment 3 also instructs the model to use only retrieved context, preserve exact clinical thresholds and dosages where present, and prioritize newer 2020/2021 guidance when relevant while noting context from older guidance.

The notebook aggregates the evaluation scores for all four configurations and visualizes them in a grouped bar chart. Exact results should be read from a fresh notebook run; scores are not hard-coded in this README.

## Setup

The notebook is designed to run in Google Colab.

1. Open the [Colab notebook](https://colab.research.google.com/drive/1ddNzy2ZydDJKKHXpsoepCxX5Oeu1UicF?usp=sharing).
2. Upload the three WHO PDF files listed above to the Colab runtime.
3. Add a Groq API key to Colab Secrets as `Groq_API_Key`, or provide it when prompted.
4. Run the notebook cells in order.

The notebook installs its Python dependencies:

```bash
pip install openai chromadb pypdf langchain-text-splitters pandas matplotlib sentence-transformers
```

**Security:** Never commit API keys or place them directly in notebook cells. Use Colab Secrets or environment variables.

## Current Scope and Limitations

- Retrieval quality is evaluated on a small six-question benchmark; the results are indicative, not a comprehensive clinical evaluation.
- LLM-as-a-Judge scores can vary and should not be treated as objective ground truth.
- PDF text extraction may not preserve every table or complex layout perfectly.
- The notebook's multi-turn chat-memory section is currently present as commented example code and is not an active, completed feature.
- A heading/subheading-based retrieval approach was described as a future experiment in the project notes; it is not implemented in this notebook.
- The system depends on external Groq model availability and API limits.

## Potential Next Steps

- Expand and independently validate the benchmark set.
- Add retrieval-specific metrics such as Recall@k, MRR, or nDCG.
- Compare chunk-based retrieval with heading/subheading-based retrieval.
- Add automated checks that verify citations against source pages.
- Implement and test multi-turn conversation memory.
- Evaluate robustness to scanned PDFs, tables, and different question formulations.

## Learning Outcomes

- Building a PDF-based RAG pipeline with page-level source metadata
- Using domain-specific embeddings locally
- Storing and retrieving embeddings with ChromaDB
- Comparing chunking and query-rewriting strategies
- Evaluating RAG responses with faithfulness, relevance, and completeness criteria
- Designing prompts for grounded answers and source citations

---
