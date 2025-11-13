## EE6483 Mini Project: Sentimental Analysis

This summary focuses on the model performance comparison and the findings from Parameter-Efficient Fine-Tuning (PEFT) experiments.

### 1. Model Performance Comparison

On the validation set, model performance was directly correlated with complexity (i.e., parameter count) and the ability to understand context.

* **Transformer (BERT) architectures** significantly outperformed the traditional baseline (TF-IDF) and the sequential model (BiLSTM).

* **BERT-Large** achieved the highest accuracy at **95.00%**, demonstrating the advantage of larger-scale pre-trained models in understanding semantic nuances.

**Validation Accuracy:**

| **Model Category** | **Model Architecture** | **Accuracy (%)** |
| :--- | :--- | :--- |
| Traditional Baseline | TF-IDF + Logistic Regression | 88.93 |
| Sequential Model | RNN (Bi-LSTM) | 91.56 |
| Transformer | DistilBERT | 93.05 |
| Transformer | BERT-Base (uncased) | 94.46 |
| **Transformer** | **BERT-Large (uncased)** | **95.00** |

### 2. The Value of Parameter-Efficient Fine-Tuning (PEFT)

We conducted an experiment on DistilBERT using LoRA (a PEFT method) and found it to be an extremely valuable compromise when resources are limited.

* **LoRA (DistilBERT)** achieved **91.15%** accuracy using only **1.09%** of the trainable parameters.

* Compared to a full DistilBERT fine-tune (93.05%), LoRA resulted in a minor accuracy loss of just 1.9% but **improved training speed by 2.36x** and was **99% more parameter-efficient**.
