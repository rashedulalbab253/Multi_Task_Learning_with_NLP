# 🧠 Multi-Task NLP with BERT

> A unified transformer-based model for **Emotion Classification**, **Violence Detection**, and **Hate Speech Detection**.
>
> ## ⚠️ Note

> My previous GitHub account was unexpectedly suspended. This project was originally created earlier and has been re-uploaded here. All work was done gradually over time, and original commit history has been preserved where possible.

---

## 🌟 Project Overview

This project implements a **multi-task learning (MTL)** framework using **BERT**, enabling one model to handle **three text classification tasks simultaneously**:

- 🎭 Emotion Recognition (joy, anger, sadness, etc.)
- 🔪 Violence Detection (binary)
- 💬 Hate Speech Identification (binary)

By sharing a common encoder and using task-specific heads, this approach improves generalization and reduces computational overhead.

---

## 🔍 Key Features

- ✅ **Multi-task architecture**: One model, multiple outputs
- ✅ **Shared BERT encoder**, fine-tuned with classification heads
- ✅ **Efficient training**: Weighted loss across tasks
- ✅ **End-to-end notebook**: Preprocessing, modeling, evaluation
- ✅ **Evaluation**: Accuracy, Macro F1-score, Confusion Matrix

---

## 🏗️ Model Architecture

```
          Input Text
              ↓
       [BERT Encoder]
              ↓
   ┌──────────┼──────────┐
   ↓          ↓          ↓
Emotion   Violence     Hate
 Head       Head        Head
```

Each head outputs predictions for its specific task. The model uses a combined loss during training.

---

## 📁 Dataset Format

The model expects data like:

| text               | emotion | violence | hate |
|--------------------|---------|----------|------|
| "What a lovely day!" | joy     | 0        | 0    |
| "I will destroy you" | anger   | 1        | 1    |

- `emotion`: Categorical label (e.g., joy, anger, fear)
- `violence`, `hate`: Binary labels (0 = no, 1 = yes)

---

## ⚙️ Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/yourusername/multi-task-nlp.git
cd multi-task-nlp
```

### 2. Install requirements

```bash
pip install -r requirements.txt
```

### 3. Run the notebook

```bash
jupyter notebook Multi_task_Learning_with_NLP.ipynb
```

> ⚠️ Use GPU for faster training (e.g., Colab or CUDA-enabled setup)

---

## 📊 Evaluation

Each task is evaluated independently using:

- ✔️ Accuracy
- ✔️ Macro F1-Score
- ✔️ Confusion Matrix
- ✔️ Visual Plots (Matplotlib/Seaborn)

---

## 📈 To-Do

- [ ] Script-based training pipeline (`train.py`)
- [ ] Support for additional languages
- [ ] API deployment with FastAPI
- [ ] Model checkpointing & export (ONNX / TorchScript)
- [ ] Experiment tracking (e.g., MLflow)

--

---
