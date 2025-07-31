# 🤖 SLA-CARA: Smart Legal Assistant for Contract Analysis and Risk Assessment

**SLA-CARA** is an end-to-end intelligent pipeline that automates legal contract analysis using cutting-edge Natural Language Processing (NLP) and Retrieval-Augmented Generation (RAG) techniques. It performs clause-level classification, summarization, risk assessment, and key legal insight extraction from legal contracts using LLaMA 3.2 and Legal-BERT.

---

## 🚀 Project Overview

Legal professionals face challenges in processing long, unstructured contracts. SLA-CARA addresses this with:

- 📄 **Automated clause extraction** from PDFs/DOCX
- 📌 **NER-based key insights detection**
- 🧠 **Legal-BERT embeddings** for clause representation
- 🔍 **FAISS + Cosine Similarity** hybrid for contextual retrieval
- 📝 **Task-specific prompting** using LLaMA 3.2
- 📊 **Multi-task outputs**: classification, summarization, risk scoring, and key entity extraction

---

## 🔁 SLA-CARA Pipeline

1. ### 📂 Preprocessing and Chunking
   - Converts uploaded PDFs/DOCX to raw text.
   - Applies NER (`Spacy - en_core_web_md`) to extract legal entities.
   - Splits content into paragraph-based clauses using regex + NLP chunking.
   - Cleans and filters unwanted characters.

2. ### 🧾 Clause Representation with Legal-BERT
   - Tokenizes each clause using `nlpaueb/legal-bert-base-uncased`.
   - Generates and normalizes embeddings for semantic similarity.

3. ### 🔎 Contextual Retrieval using FAISS + Cosine Similarity
   - FAISS retrieves top-k² nearest neighbors.
   - Cosine similarity refines and reranks relevant clauses.

4. ### 🧠 Prompting LLaMA 3.2 via Lambda API
   - Custom prompts crafted for each legal task.
   - Prompts include clause, context, task instructions, and formatting guidance.

5. ### 📤 Response Generation
   - LLaMA 3.2 returns structured outputs for:
     - **Clause Classification**
     - **Plain Language Summarization**
     - **Risk Labeling**
     - **Entity Extraction**

---

## 📊 Performance & Evaluation

- **Contextual Retrieval:** Recall@5 = 77.1%
- **Clause Classification:** Accuracy = 66% | Weighted F1 = 0.67
- **Risk Analysis:** Strong precision for Confidentiality & Termination clauses
- **Summarization:**
  - ROUGE-1: 0.5015
  - ROUGE-2: 0.3251
  - ROUGE-Lsum: 0.4569
  - BLEU: 0.2435

---

## 📁 Dataset

- 📘 **CUAD v1**: Contract Understanding Atticus Dataset from The Atticus Project
- Contains:
  - 510 contracts (PDF/TXT)
  - 13K+ labeled clauses
  - 41 clause types

---

## 🛠️ Technologies Used

| Component        | Technology                          |
|------------------|-------------------------------------|
| LLM API          | LLAMA 3.2 via Lambda Labs           |
| NLP & NER        | SpaCy (`en_core_web_md`)            |
| Tokenizer        | HuggingFace AutoTokenizer           |
| Embedding Model  | `legal-bert-base-uncased`           |
| Vector DB        | FAISS                               |
| UI               | Python Streamlit                    |

---

## 🧩 Tasks Performed

- ✅ Contract Clause Classification
- ✅ Clause Summarization
- ✅ Legal Risk Detection (e.g., IP Risk, Liability)
- ✅ Key Legal Insights (Parties, Dates, Obligations)

---

## 📷 Pipeline Flow Diagram

<img width="476" height="904" alt="image" src="https://github.com/user-attachments/assets/008be830-7db8-44fe-956e-6ff4c0ba6522" />

---

## 📈 Future Enhancements

- 🌐 Multilingual Legal Document Support
- 🔒 Legal Compliance Engine Integration
- 📚 Expand dataset using SEC/EDGAR annotated contracts

---
