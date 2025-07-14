# 🧪 Variant Analysis with Evo2 – Modal + Next.js

A full-stack bioinformatics project for **gene variant effect prediction**, powered by the **Evo2 large language model** from Arc Institute. This project features:

* A **Next.js (React)** frontend
* A **FastAPI backend** deployed with **Modal** (H100 GPU)
* Deep analysis and classification of genetic variants (e.g. BRCA1)

---

## 🔬 Overview

This application fetches gene sequences (e.g. from UCSC), runs inference on genetic variants using Evo2 (LLM for genomics), and provides visualizations and classification:

*  Variant classification as Likely Pathogenic or Benign
*  Interactive analysis and scoring
*  BRCA1 demo plot and AUROC calculation
*  HuggingFace caching for model reuse

---

## 🗂 Project Structure

```
VARIENT-ANALYSIS-EVO2/
├── EVO2Backend/                # Python + Modal-based Evo2 FastAPI API
│   ├── main.py                 # Deployment entrypoint for Modal
│   ├── requirements.txt        # Python dependencies
│   └── evo2/                   # Evo2 source code
│
├── EVO2frontend/              # Next.js React frontend
│   ├── app/                    # Routing + pages
│   ├── components/            # UI components
│   ├── styles/                # Tailwind CSS styling
│   └── utils/                 # API utility functions
```

---

## 🚀 Deployment

### 🔧 Backend (Modal)

> Deployed on Modal with GPU (H100) using FastAPI endpoints

1. Install dependencies:

   ```bash
   pip install modal
   ```

2. Authenticate:

   ```bash
   modal token new
   ```

3. Deploy:

   ```bash
   modal deploy main.py
   ```

You will receive a FastAPI endpoint like:

```bash
POST https://variant-analysis-evo2--analyze-single-variant.modal.run/
```

---

## 📈 Example Output

* Delta scores for BRCA1 SNVs
* AUROC of Evo2 on known BRCA1 dataset
* Variant class prediction (LOF vs FUNC/INT)
* Visualization with seaborn + matplotlib

---

## 🛆 Requirements (Backend)

```txt
fastapi[standard]
numpy<2.0
matplotlib
pandas
seaborn
scikit-learn
openpyxl
biopython
```

---

## 🤖 Evo2 Model Details

* Model: `evo2_7b`
* Source: [https://github.com/ArcInstitute/evo2](https://github.com/ArcInstitute/evo2)
* GPU: H100 via Modal
* Transformer Engine: `transformer_engine[pytorch]`

---

## 🎜 License

MIT License © 2025 – Variant Analysis Evo2 Team

---

## 👩‍⚖️ Authors

* Modal Deployment: `@arpit`
* Evo2 Integration: Arc Institute (model authorship)
* Frontend UI: Next.js + Tailwind by the team

---
