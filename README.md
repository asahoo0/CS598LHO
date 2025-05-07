# 💤 SleepQA Reproducibility Project

This repository contains code and documentation for reproducing major components of the SleepQA paper, including text preprocessing, sparse/dense retrieval pipelines, and evaluation with domain-specific BERT models.

## 📁 Repository Structure

- `CleanedCode.ipynb` – Master notebook to run everything (excluding PyHealth)
- `sleepQADataProcessing.ipynb` – Dataset processing and cleaning
- `tfidf.ipynb` – TF-IDF based retrieval and ablation study
- `models.ipynb` – Extractive QA with domain-specific BERTs
- `pipelines.ipynb` – Sparse (BM25) and dense (Faiss) retrieval pipelines
- `PyHealth/`
  - `pyhealth.ipynb`, `sleepQA.yaml`
- `requirements.txt` – List of required packages
- `README.md` – You are here!

## ✅ Environment & Dependencies

All notebooks are runnable independently. To reproduce the full pipeline, use `CleanedCode.ipynb` (except for `PyHealth`, which is separate).

**Recommended environment**: Google Colab with T4 GPU.

## 📦 Required Packages

Install the following packages:<br>

transformers<br>
sentence-transformers<br>
torch<br>
faiss-cpu<br>
pandas<br>
scikit-learn<br>
datasets<br>
matplotlib<br>
tqdm<br>
rake-nltk<br>
rank_bm25<br>

🚀 How to Use<br>
🔹 Full Reproduction Pipeline<br>
Run CleanedCode.ipynb to execute:<br>

Article processing (cleaning, chunking, title generation)<br>

Sparse retrieval (BM25Okapi)<br>

Dense retrieval (Faiss + BERT)<br>

Extractive QA (BioBERT and other BERT variants)<br>

🔹 Individual Notebooks
sleepQADataProcessing.ipynb: Cleans and chunks article text

tfidf.ipynb: Implements TF-IDF baseline and ablation

pipelines.ipynb: Implements BM25 + BioBERT and Faiss-based dense retrieval

models.ipynb: Runs multiple BERT-based QA models including BioBERT, PubMedBERT, ClinicalBERT, etc.

PyHealth/: (Optional) Generates datasets using the PyHealth library — separate from SleepQA

⚠️ Notes
Pyserini (Lucene BM25) could not be used due to incompatibility with Google Colab. BM25Okapi was used as a functional substitute.

All notebooks are designed for Colab and are compatible with GPU (T4) runtime.

## 📜 Citation

Bojic, I., Ong, Q.C., Thakkar, M., Kamran, E., Shua, I.Y.L., Pang, J.R.E., Chen, J., Nayak, V., Joty, S., & Car, J. (2022).  
**SleepQA: A Health Coaching Dataset on Sleep for Extractive Question Answering.**  
*Proceedings of the 2nd Machine Learning for Health Symposium, in Proceedings of Machine Learning Research*, **193**, 199–217.  
Available from: [https://proceedings.mlr.press/v193/bojic22a.html](https://proceedings.mlr.press/v193/bojic22a.html)

