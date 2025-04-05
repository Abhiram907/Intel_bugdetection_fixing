# 🔎 Bug Detection and Fixing in Java Code using CodeT5 + QLoRA

This project focuses on detecting bugs and fixing them automatically in Java programs using deep learning techniques. 
We fine-tune the CodeT5 model with QLoRA (Quantized Low-Rank Adaptation) for efficient training. 
The final model is capable of both detecting buggy code and suggesting fixes with high BLEU scores.

---
## Dataset

The dataset used for this project is the [CodeXGLUE Code-Refinement Dataset (Medium Size)](https://github.com/microsoft/CodeXGLUE/tree/main/Code-Refinement).
It consists of Java source code snippets, each provided in two forms:
- **Buggy Version**: Code containing one or more bugs.
- **Fixed Version**: The corrected version of the buggy code.

- Total Samples: **52,364** buggy-fixed code pairs for training.
## Problem Statement

The goal of this project is two-fold:

1. **Bug Fixing**: Given buggy Java code, generate the correct fixed version of the code.
2. **Bug Detection**: Identify whether a given Java code snippet is buggy or clean.

The tasks involve:
- Detecting and understanding bugs in Java source code.
- Correcting the code with minimal changes.
- Evaluating model performance using standard NLP metrics like BLEU score and classification metrics like Accuracy, Precision, Recall, and F1-score.

This project aims to assist developers by automating parts of the bug fixing and detection processes, improving code quality and productivity.

## Problem Statement

The goal of this project is two-fold:

1. **Bug Fixing**: Given buggy Java code, generate the correct fixed version of the code.
2. **Bug Detection**: Identify whether a given Java code snippet is buggy or clean.

The tasks involve:
- Detecting and understanding bugs in Java source code.
- Correcting the code with minimal changes.
- Evaluating model performance using standard NLP metrics like BLEU score and classification metrics like Accuracy, Precision, Recall, and F1-score.

This project aims to assist developers by automating parts of the bug fixing and detection processes, improving code quality and productivity.
## Models Used

- **CodeBERT** (`microsoft/codebert-base`): Used for initial experiments in code understanding and tokenization.

- **CodeT5** (`Salesforce/codet5-base`): Used for both Bug Fixing and Bug Detection tasks. It provided better support for sequence-to-sequence learning and generation.

- **QLoRA**: (Quantized LoRA) technique was optionally applied to fine-tune models efficiently with reduced GPU memory consumption, making training scalable on limited hardware.
## Training Details

- **Bug Fixing Task**:
  - Model: CodeT5 (fine-tuned with QLoRA)
  - Tokenizer: CodeBERT
  - Number of Training Samples: 52,364
  - Preprocessing: Buggy and fixed code pairs were preprocessed and tokenized.
  - Evaluation Metric: BLEU Score (achieved 91.03)

- **Bug Detection Task**:
  - Model: CodeT5
  - Data Preparation: Buggy and fixed code converted into a binary classification dataset.
  - Labels: 
    - `0` → No bug (fixed code)
    - `1` → Buggy code
  - Training Method: Trainer API from Huggingface.
  - Metric: Accuracy and Loss
## Evaluation Metrics

For Bug Fixing:
- **BLEU Score**: Achieved a BLEU score of **91.03** on the test dataset.

For Bug Detection:
- **Accuracy**: Measured how well the model classifies buggy and non-buggy code.
- **Precision, Recall, F1-Score**: Evaluated using standard classification metrics.

Graphs (optional):
- Loss vs Epochs plot.
- Accuracy vs Epochs plot.

## Results

- **Bug Fixing**:
  - BLEU Score: 91.03 ✅
  
- **Bug Detection**:
  - High classification accuracy observed during evaluation.

The models show strong performance in both tasks.
## Conclusion

This project successfully tackled two important tasks on Java code:

- **Bug Fixing**: Using CodeT5 fine-tuned with QLoRA, we achieved a BLEU score of **91.03** on the test set, indicating strong model performance in fixing buggy code samples.
- **Bug Detection**: The model was trained to classify whether a code snippet is buggy or clean with high accuracy.

The use of lightweight fine-tuning (QLoRA) allowed efficient training even with limited resources, while still achieving strong results. This shows that foundation models like CodeT5 can be highly effective for software engineering tasks with proper adaptation.

Further improvements can be made by:
- Using larger or domain-specific datasets.
- Exploring other models like CodeLlama, or more specialized LLMs for programming languages.
- Applying techniques like data augmentation or prompt tuning.
## Future Work

- **Expand Dataset**: Incorporate more programming languages (e.g., Python, C++) to make the model more generalizable.
- **Error Analysis**: Perform a deeper manual analysis on wrong predictions to understand model limitations better.
- **Model Enhancements**:
  - Try larger models like CodeT5+ or CodeLlama-13B with efficient fine-tuning methods.
  - Experiment with Retrieval-Augmented Generation (RAG) for better bug detection.
- **Real-world Integration**:
  - Deploy the bug detection and fixing model as an API.
  - Build a simple VSCode plugin for automated code review.
- **Evaluation Improvements**:
  - Incorporate additional metrics such as CodeBLEU, Exact Match (EM), and edit distance.


