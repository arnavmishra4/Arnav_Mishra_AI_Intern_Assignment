# Arnav_Mishra_AI_Intern_Assignment

# 🚀 RAG System Implementation

**Retrieval-Augmented Generation Pipeline for Document Q&A**

Built a production-grade RAG system that processes Dr. B.R. Ambedkar's speeches, creates semantic embeddings, and enables intelligent question-answering with comprehensive evaluation.

---

## 📦 Tech Stack

- **LLM**: Mistral (via Ollama)
- **Embeddings**: sentence-transformers/all-MiniLM-L6-v2
- **Vector Store**: ChromaDB
- **Framework**: LangChain
- **Metrics**: ROUGE-L, BLEU, Cosine Similarity, Hit Rate, MRR, Precision@K, Answer Relevance, Faithfulness

---

## 📂 Structure

```
├── assignment1.ipynb       # Basic RAG pipeline
├── assignment2.ipynb       # Advanced RAG + evaluation
├── speech.txt              # Single document (Assignment 1)
├── corpus/                 # Multiple documents (Assignment 2)
├── test_question.json      # Test dataset
├── test_results.json       # Evaluation results
└── README.md
```

---

## 🎯 Assignment 1: Basic RAG

**What I Built:**

1. **Document Processing** - Loaded and chunked text (100 chars, 40% overlap)
2. **Embeddings** - Generated 384-dim semantic vectors
3. **Vector DB** - ChromaDB with persistent storage
4. **Semantic Search** - Top-3 retrieval via cosine similarity
5. **LLM Integration** - Mistral for grounded answer generation
6. **Source Tracking** - Full transparency on retrieved documents

**Example Query:**  
*"What is the real remedy for caste system?"*  
→ Query embedding → Vector search → Context + LLM → Grounded answer

---

## 🚀 Assignment 2: Advanced RAG + Evaluation

### Multi-Document System
- Processes entire corpus directory
- Metadata tracking per chunk
- Top-5 retrieval for better coverage
- Scalable architecture

### 8-Metric Evaluation Framework

**Retrieval Quality**
- **Hit Rate** - Did we find the right document?
- **MRR** - How well ranked is the correct document?
- **Precision@K** - Percentage of relevant documents retrieved

**Generation Quality**
- **ROUGE-L** - Longest common subsequence overlap
- **BLEU** - N-gram precision
- **Cosine Similarity** - Semantic similarity to ground truth

**RAG Integrity**
- **Answer Relevance** - Is the answer on-topic?
- **Faithfulness** - Is the answer grounded in context?

### Chunk Size Optimization

Tested **300 / 600 / 900** character chunks with full metric analysis:

| Size | Trade-off |
|------|-----------|
| 300  | High precision, focused context |
| 600  | Balanced approach |
| 900  | Rich context, potential noise |

---

## 🏗️ System Architecture

```
📁 Input Documents
      ↓
📊 Text Chunking
      ↓
🧮 Embedding Generation (all-MiniLM-L6-v2)
      ↓
💾 Vector Storage (ChromaDB)
      ↓
🔍 Query → Semantic Retrieval (Top-K)
      ↓
🤖 LLM Generation (Mistral + Context)
      ↓
📋 Grounded Answer + Sources
      ↓
📊 8-Metric Evaluation
```

---

## 🔮 Future Enhancements

- **Fine-Tuning** - Domain-specific SFT on Ambedkar corpus
- **RLHF** - Reward modeling for faithfulness optimization
- **Hybrid Search** - Combine BM25 + semantic search
- **Re-ranking** - Cross-encoder for precision
- **W&B Integration** - Experiment tracking
- **Production API** - FastAPI + Docker deployment

---

## 🎯 Key Results

✅ End-to-end RAG pipeline from raw text to evaluated answers  
✅ 8-metric evaluation across retrieval, generation, and RAG quality  
✅ Systematic chunk size optimization with quantitative analysis  
✅ Multi-document corpus support with source attribution  
✅ Production-ready modular architecture

---

## 🚀 Quick Start

1. **Prerequisites**: Python 3.8+, Ollama with Mistral
2. **Run**: Open `assignment1.ipynb` or `assignment2.ipynb`
3. **Results**: View metrics in `test_results.json`

---

## 💡 Technical Highlights

| Area | Implementation |
|------|----------------|
| **LLM** | Local Mistral deployment (privacy + no API costs) |
| **Embeddings** | 384-dim vectors, fast inference |
| **Vector DB** | HNSW indexing for efficient search |
| **Evaluation** | Multi-metric framework prevents blind spots |
| **Architecture** | Modular, scalable, configuration-driven |

---

**Status**: ✅ Ready for Review  
**Code Quality**: Clean, documented, reproducible  
**Extensibility**: SFT, RLHF, production deployment ready
