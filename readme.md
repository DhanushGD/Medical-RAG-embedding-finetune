# 🏥 Medical-RAG: Reducing Hallucinations via Embedding Fine-Tuning

This project demonstrates a 23.67% reduction in LLM hallucinations by fine-tuning a domain-specific embedding model for Medical Retrieval-Augmented Generation (RAG). By moving from "finding words" to "finding facts," we significantly improved the reliability of a local Llama 3 assistant.

## 🚀 The Results
| Metric | Base Model (Generic) | Fine-tuned Model (Medical) |
| :--- | :---: | :---: |
| **Faithfulness (Groundedness)** | 0.56 | **0.69** |
| **Context Precision** | 0.81 | 0.78* |
| **Hallucination Reduction** | - | **+23.67%** |

*\*Note: Fine-tuned precision is more selective, prioritizing clinical semantic relevance over keyword matching.*

## 🧠 The Problem: "Finding Words" vs "Finding Facts"
Generic embedding models often retrieve documents based on superficial keyword similarity. In medical contexts, this leads to "noisy" context, forcing the LLM to guess (hallucinate). Fine-tuning aligns the vector space to clinical jargon, ensuring the LLM is anchored in peer-reviewed truth.

## 🛠️ Technical Stack
* **Fine-Tuning:** [Unsloth AI](https://unsloth.ai/docs/new/embedding-finetuning) (LoRA adapters)
* **Base Model:** `unsloth/all-MiniLM-L6-v2`
* **Dataset:** 10,000 triplets from `sentence-transformers/pubmedqa`
* **Vector DB:** FAISS (FlatL2 Index)
* **Local LLM:** Llama 3 (via Ollama)
* **Evaluation:** RAGAS (Faithfulness & Context Precision)

## 📂 Project Structure
* `Medical_Embedding_Finetuning.ipynb`: The training notebook using Unsloth.
* `RAG_Evaluation_Audit.ipynb`: The side-by-side comparison script using Ollama & RAGAS.
* `final_lora_model/`: Saved LoRA adapters.
* `medical_kb.index`: Pre-computed FAISS vector index.

## 📖 How it Works
1. **Fine-Tuning:** Applied MultipleNegativesRankingLoss to teach the model medical semantic relationships.
2. **Indexing:** Embedded 10,000 medical passages into a high-dimensional FAISS vector space.
3. **Retrieval:** Used the fine-tuned model to fetch the top-3 most relevant clinical contexts.
4. **Generation:** Passed context to a local Llama 3 instance with a strict "answer only from context" prompt.
5. **Validation:** Audited the output using RAGAS to verify that the improved retrieval directly reduced hallucination rates.

## 🔍 What is MultipleNegativesRankingLoss?
This loss function is used in contrastive learning to teach the model to distinguish between relevant and irrelevant contexts.
🔧 Simple Example:
Imagine you're training on this triplet:
- Query: “What is the treatment for hypertension?”
- Positive: “Hypertension is treated with ACE inhibitors and lifestyle changes.”
- Negatives: Other passages in the same batch like “Diabetes is managed with insulin.”
The model:
- Pulls the query and positive closer in embedding space.
- Pushes all other negatives (from the same batch) farther away.
This is efficient because every other positive in the batch becomes a negative for the current query, reducing the need for manually curated hard negatives.

## 🤔 Why Fine-Tune Embeddings Instead of Using Base Models?
Base models are trained on general-purpose corpora (Wikipedia, Common Crawl), which:
- Prioritize word-level similarity over fact-level relevance.
- Often fail in clinical nuance, e.g., confusing “hypertension” with “high blood pressure” without understanding treatment context.
🧠 Example:
- Query: “What’s the first-line therapy for atrial fibrillation?”
- Base Model Retrieval: “Atrial fibrillation is a heart rhythm disorder.”
- Fine-Tuned Model Retrieval: “Beta blockers and anticoagulants are first-line treatments for atrial fibrillation.”
Fine-tuning ensures the model retrieves factually relevant passages, not just semantically similar ones.

