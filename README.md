
#  Spooky Author Attribution

A **BERT-based NLP project** for **authorship attribution** based on the Kaggle **Spooky Author** dataset, enhanced by additional literary works from the authors themselves. This project aims to classify excerpts from texts written by three renowned classic horror authors.

---

##  Project Overview

The goal of this project is to determine the author of a given text snippet among these three famous horror authors:

-  **H.P. Lovecraft (HPL)**
-  **Edgar Allan Poe (EAP)**
-  **Mary Wollstonecraft Shelley (MWS)**

The original dataset from Kaggle was expanded significantly by scraping and processing additional texts from each author's published books, resulting in a richer and larger dataset.

###  Dataset

The dataset is split as follows:

| Split         | Number of samples |
|---------------|-------------------|
| Train         | 38,374            |
| Validation    | 4,797             |
| Test          | 4,797             |

Each data entry contains:
- **id**: Unique identifier for the text
- **text**: The excerpt from the author's literary works
- **author**: The author (HPL, EAP, MWS)

###  Methodology

**Data Preprocessing**
- Text tokenization and encoding were performed using the **BERT Tokenizer**.

**Model**
- Base Model: `bert-base-uncased`
- Custom Classification Head:
  - Linear layers: 512 -> 256 -> 128 -> Output (3 classes)
  - Activation: ReLU
  - Regularization: Batch normalization and dropout (50% dropout)

**Training**
- Optimizer: AdamW
- Learning rates:
  - BERT layers: `2e-5`
  - Dense layers: `1e-3`
- Loss function: Cross-entropy
- Gradient clipping for stability

**Evaluation**
- Validation accuracy: approximately **89%**
- Detailed classification metrics (precision, recall, F1-score) provided through sklearn's classification report

---

##  Libraries Used

- `transformers` (for BERT and tokenization)
- `torch` (PyTorch for model implementation and training)
- `pandas` (Data loading and manipulation)
- `scikit-learn` (Metrics and label encoding)
- `tqdm` (Progress bar utility)

---

##  Project Structure

```
.
├── train.csv
├── val.csv
├── test.csv
├── spooky_author.ipynb
└── README.md
```

---

##  Results

| Metric      | Validation Accuracy |
|-------------|---------------------|
| BERT Model  | ~89%                |

The detailed results including precision, recall, and F1-scores are available in the notebook.

---

##  Future Enhancements

- Utilize more advanced language models (e.g., RoBERTa, GPT-based models)
- Incorporate model interpretability methods (attention visualization)
- Ensemble multiple NLP models to enhance accuracy

---

##  Project by

**Danial Ebrazeh** *(SCU Student)*  
Data augmentation sourced from publicly available literary texts.
