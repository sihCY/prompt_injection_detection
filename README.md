# 🚫 prompt_injection_detection

This repository contains the MalPID dataset proposed in the paper https://ieeexplore.ieee.org/abstract/document/10987374 that can be used to train detectors of prompt injection attacks in language model inputs. It also includes the used source code to train and test the performance of two ML models—**Logistic Regression** and **ALBERT**—on a curated dataset of legitimate and malicious prompts.

## 📁 Files

- **`MalPID_dataset.csv`**  
  A labeled dataset of prompts, including both benign and malicious examples intended for training and testing prompt injection detection models.

- **`classify_maliciousContent.ipynb`**  
  A Jupyter Notebook containing the full pipeline:
  - Data preprocessing
  - Feature extraction
  - Model training and evaluation  
  It includes implementations for:
    - **Logistic Regression** using [scikit-learn](w)
    - **ALBERT** using [Hugging Face Transformers](w)

## 🧠 Models Used

### 1. [Logistic Regression](w)
- Implemented using the `scikit-learn` library.
- **Uses sentence embeddings** obtained via [`SentenceTransformer('all-MiniLM-L6-v2')`](w) from the [Sentence-Transformers](w) library.
- Quick to train and performs well on smaller datasets.

### 2. [ALBERT](w) (A Lite BERT)
- A lightweight transformer-based model from Hugging Face.
- Fine-tuned on the `MalPID_dataset.csv` for binary classification.
- More computationally expensive but capable of capturing deeper contextual meaning.

## 📊 Results

Both models were evaluated using metrics such as accuracy, precision, recall, and F1-score. Results are visualized in the notebook for comparative analysis.

## 📦 Dependencies

To run the notebook, install the following (preferably in a virtual environment):

```bash
pip install scikit-learn pandas numpy matplotlib seaborn transformers torch sentence-transformers
