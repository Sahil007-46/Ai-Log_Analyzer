# AI Log Intelligence & Incident Detection System (AIOps)

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![LangChain](https://img.shields.io/badge/LangChain-Enabled-green.svg)
![ChromaDB](https://img.shields.io/badge/ChromaDB-Vector_Store-orange.svg)

An enterprise-grade Retrieval-Augmented Generation (RAG) pipeline designed to ingest, process, and classify massive AWS Landing Zone Accelerator (LZA) logs. This system leverages Large Language Models (LLMs) and vector databases to automate root-cause analysis and distinguish routine infrastructure changes from critical security risks.

## 🚀 Core Capabilities

* **Accurate Log Querying:** Engineered a RAG pipeline utilizing Python, LangChain, and a ChromaDB vector database to eliminate LLM hallucinations and enable highly accurate querying of complex AWS LZA logs.
* **Optimized Context Retrieval:** Implemented semantic chunking and Hybrid Search, leveraging the `all-MiniLM-L6-v2` embedding model to convert complex ASCII tables and nested JSON conditions into searchable mathematical vectors.
* **Automated Incident Response:** Accelerated incident response times by injecting retrieved log context into an LLM, automating the precise classification of routine formatting changes versus critical infrastructure security risks.

## 🏗️ System Architecture

1. **Log Ingestion:** Parses raw, massive AWS LZA log files and complex JSON structures.
2. **Semantic Chunking (`chunker.py`):** Intelligently splits logs into meaningful, context-aware segments rather than arbitrary text splits, preserving the integrity of ASCII tables and nested configurations.
3. **Embedding Generation (`embeddings.py`):** Converts the text chunks into mathematical vectors using the `all-MiniLM-L6-v2` sentence-transformer model.
4. **Vector Storage (`vector_store.py`):** Indexes the embeddings into a local ChromaDB instance for rapid, low-latency similarity search.
5. **RAG Pipeline & Classification (`langchain_rag.py` & `report_generator.py`):** Retrieves the most relevant log context based on the incident query and injects it into the LLM to generate precise, hallucination-free risk classifications and reports.

## 🛠️ Tech Stack

* **Language:** Python
* **Orchestration:** LangChain
* **Vector Database:** ChromaDB
* **Embeddings:** `all-MiniLM-L6-v2` (Sentence Transformers)
* **Dependency Management:** `uv` / `pyproject.toml`

## 📁 Repository Structure

\`\`\`text
├── pyproject.toml               # Project metadata and dependencies
├── uv.lock                      # Exact dependency versions
├── llm_config.yaml              # Configuration for LLMs and embeddings
├── resource_categorization.yaml # Business logic for incident detection
├── src/
│   ├── langchain_rag.py         # Core RAG orchestration 
│   ├── vector_store.py          # ChromaDB integration
│   ├── chunker.py               # Semantic log splitting logic
│   ├── embeddings.py            # Embedding model initialization
│   └── report_generator.py      # Automated classification output
└── sample_incident_report.html  # Visual proof of automated output
\`\`\`

## ⚙️ Getting Started

### Prerequisites
Ensure you have Python 3.9+ installed. This project uses [uv](https://github.com/astral-sh/uv) for lightning-fast dependency management.

### Installation

1. Clone the repository:
   \`\`\`bash
   git clone https://github.com/Sahil007-46/LZA-Log-Analyzar.git
   cd LZA-Log-Analyzar
   \`\`\`

2. Install dependencies using `uv` (or pip):
   \`\`\`bash
   # If using uv
   uv pip install -r pyproject.toml
   
   # Or using standard pip
   pip install .
   \`\`\`

### Usage
*(Note: Replace with the actual command to run your main script once configured)*
\`\`\`bash
# Example command to run the pipeline
python src/langchain_rag.py --config llm_config.yaml
\`\`\`
