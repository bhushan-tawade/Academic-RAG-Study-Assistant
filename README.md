# 📚 RAG-Based Academic Study Assistant (Machine Learning)

An AI-powered **Retrieval-Augmented Generation (RAG)** system designed to answer **Machine Learning (ML)** academic questions using structured chapter-wise PDF materials.

This project demonstrates a complete end-to-end RAG pipeline including:

- 📄 PDF ingestion
- 🧮 Equation-aware preprocessing
- ✂️ Intelligent chunking strategies
- 🔎 Semantic retrieval
- 🧠 Embedding generation
- 🗄 Vector database storage
- 🤖 LLM-based grounded answer generation
- 📊 Source tracking with confidence scoring

---

# 🎯 Project Objective

To build an AI-powered academic assistant capable of:

- Answering conceptual Machine Learning questions
- Explaining mathematical derivations
- Retrieving relevant textbook sections
- Providing context-grounded responses
- Handling formula-heavy ML content

This project specifically focuses on **Machine Learning domain knowledge retrieval**.

---

# 📂 Dataset Details (Machine Learning Domain)

The dataset consists of structured chapter-wise PDF notes covering core ML topics.

## 📘 Included Chapters

1. Introduction to Machine Learning  
2. Simple Linear Regression  
3. Logistic Regression  
4. Decision Trees  
5. Neural Networks  
6. Overfitting & Regularization  
7. Bias-Variance Tradeoff  
8. Gradient Descent  
9. Evaluation Metrics  

## 📊 Dataset Characteristics

- **Format:** PDF  
- **Domain:** Machine Learning  
- **Content Includes:**
  - Theoretical explanations
  - Mathematical derivations
  - Optimization formulas
  - Model definitions
  - Algorithm descriptions
  - Evaluation metrics

Some chapters contain heavy mathematical notation and symbolic expressions.

---

# 🏗 System Architecture

1. PDF Documents  
2. Equation Preprocessing  
3. Chunking (Fixed-size / Sentence-based)  
4. Embedding Generation (SentenceTransformer)  
5. ChromaDB Vector Store  
6. Custom Retriever  
7. LLM (Groq - LLaMA 3.1)  
8. Final Answer + Sources + Confidence  


---

# 🧠 Key Features

## 1️⃣ Equation-Aware Preprocessing

- Greek symbol normalization
- Mathematical operator normalization
- Superscript handling
- Whitespace cleanup
- Text standardization

This improves embedding quality for formula-based queries such as:

- Least Squares Estimation  
- Gradient Descent update rules  
- Logistic Regression equations  

---

## 2️⃣ Dual Chunking Strategies

### 🔹 Fixed-Size Chunking
- Overlap-based
- Balanced retrieval
- Good for dense technical content

### 🔹 Sentence-Based Chunking
- Preserves semantic boundaries
- Better for theory-heavy explanations
- Improves contextual clarity

---

## 3️⃣ Custom Embedding Manager

- Uses `all-MiniLM-L6-v2`
- Batch embedding generation
- Efficient vector handling
- Clean object-oriented implementation

---

## 4️⃣ Persistent Vector Store (ChromaDB)

- Stores embeddings locally
- Metadata enrichment
- Fast similarity search
- Scalable design

---

## 5️⃣ Advanced RAG Pipeline

Features include:

- Top-k retrieval
- Similarity score threshold filtering
- Source tracking
- Confidence scoring
- Context-restricted LLM responses
- Hallucination control through prompt engineering

---


# 📦 Project Structure

RAG-Academic-Study-Assistant/  
│  
├── data/  
│ ├── pdf/ # ML Chapter PDFs  
│ ├── text_files/ # Sample text files (demo)  
│ └── vector_store/ # Generated vector DB (ignored in Git)  
│  
├── notebooks/  
│ └── rag_pipeline.ipynb  
│  
├── main.py  
├── requirements.txt  
├── README.md  
├── .env.example  
└── .gitignore


---

# ⚙️ Installation Guide (Using uv - Recommended)

This project uses **uv** for fast and reproducible dependency management.

---

## 1️⃣ Install Python (If Not Installed)

Make sure Python 3.11 is installed.

**Check version:**

```bash
python --version
```

## 2️⃣ Install uv (If Not Installed)

```bash
pip install uv
```

**Verify installation:**
```bash
uv --version
```

## 3️⃣ Clone Repository
```bash
git clone https://github.com/bhushan-tawade/Academic-RAG-Study-Assistant.git  
cd Academic-RAG-Study-Assistant
```
## 4️⃣ Create Virtual Environment (uv way)
```bash
uv venv
```
This creates a .venv/ directory.

## 5️⃣ Install Dependencies
If the repository contains a `uv.lock` file (recommended):
```bash
uv sync
```
**This installs exact locked versions ensuring:**
- No dependency conflicts
- No version mismatch
- Fully reproducible setup  

If using requirements.txt instead:
```bash
uv pip install -r requirements.txt
```

## 6️⃣ Activate Virtual Environment  
**Windows:**
```bash
.venv\Scripts\activate
```

**Mac/Linux:**
```bash
source .venv/bin/activate
```

You should see:
```bash
(.venv)
```
## 7️⃣ Set Environment Variables 
Create a `.env` file in the root directory:
```bash
GROQ_API_KEY=your_groq_api_key_here
```

## 8️⃣ (Recommended) Register Jupyter Kernel  
To ensure Jupyter uses the correct environment:
```bash
python -m ipykernel install --user --name rag-env --display-name "RAG-Env"
```

Then in Jupyter:

Kernel → Change Kernel → Select RAG-Env

## 9️⃣ Run the Notebook
Start Jupyter:
```bash
jupyter notebook
```
Open:
```bash
notebooks/rag_pipeline.ipynb
```

### Run cells step-by-step:

- Data ingestion
- Equation preprocessing
- Chunking
- Embedding generation
- Vector store creation
- Retrieval
- RAG testing


