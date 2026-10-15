# Sentinel Advanced RAG Engine

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Architecture](https://img.shields.io/badge/Architecture-Modular%20RAG-orange)
![License](https://img.shields.io/badge/License-MIT-green)

A modular, production-ready **Retrieval-Augmented Generation (RAG)** pipeline optimized for compliance, legal standards, and complex enterprise technical documentation.

---

## 📌 Architecture Overview

Hệ thống triển khai kiến trúc Advanced RAG hai giai đoạn (Two-Stage Pipeline) kết hợp giữa tìm kiếm từ khóa và ngữ nghĩa đa tầng:

[User Query]
│
▼
[Query Transformation & Expansion]
│
├───► [BM25 Sparse Keyword Retriever] ──────┐
│ ├──► [Reciprocal Rank Fusion (RRF)] ──► [Cross-Encoder Reranker] ──► [LLM Generation]
└───► [Dense Vector Search (Qdrant)] ───────┘

## 🚀 Key Features

- **Hybrid Search Engine:** Kết hợp Sparse Keyword Search (BM25) với Dense Semantic Search thông qua giải thuật **Reciprocal Rank Fusion (RRF)**.
- **Context-Aware Cross-Encoder Reranking:** Tái đánh giá mức độ phù hợp thực tế của từng đoạn văn bản trước khi đưa vào context window của LLM, hạn chế tối đa ảo giác (hallucination).
- **Hierarchical Chunking:** Phân đoạn văn bản đa cấp bảo toàn cấu trúc phân mục của văn bản quy phạm, tiêu chuẩn và điều khoản.
- **Quantitative Benchmark Pipeline:** Tích hợp bộ đánh giá tự động dựa trên `GROUND_TRUTH.md` nhằm đo lường:
  - _Context Precision_
  - _Context Recall_
  - _Faithfulness_
  - _Answer Relevance_

## 📂 Project Structure

```text
sentinel-advanced-rag/
├── backend/
│   ├── app/                   # API services & application logic
│   ├── eval/                  # Evaluation schemas & testing harness
│   ├── poc/                   # Knowledge graph & retrieval components
│   └── requirements.txt       # Core dependencies
├── data/
│   └── compliance_corpus/     # Corpus dữ liệu chuẩn và GROUND_TRUTH.md
├── config/                    # Cấu hình pipeline & model settings
├── .gitignore
├── LICENSE
└── README.md
```
