## Comparison: RAG vs Fine-Tuned LLM  

| Feature                | RAG-based Approach (`pdf_rag_question_generator.ipynb`) | Fine-Tuned LLM (`pdf_finetuned_llm_question_generator.ipynb`) |
|------------------------|-------------------|------------------------------------------------------|
| Retrieval Method      | FAISS + Semantic Search | N/A |
| Embedding Model       | `sentence-transformers/all-mpnet-base-v2` | N/A |
| Question Generation   | Google Gemini API | Mistral-7B (Fine-tuned) *(⚠️ Not fully implemented due to resource limitations)* |
| Dependency on Context | High (Retrieves relevant chunks) | Medium (Processes full text directly) |
| Accuracy & Relevance  | Moderate | Potentially High (Needs fine-tuning) |
| Computational Cost    | Lower | High *(⚠️ Requires more resources for training & inference)* |

---

⚠️ **Note:** The **fine-tuned LLM approach** is not fully implemented due to **hardware limitations**. The model requires **higher computational resources**, making it difficult to run on standard CPUs. Further optimization or cloud-based deployment is needed to complete the implementation.
