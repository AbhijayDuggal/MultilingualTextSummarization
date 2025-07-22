# MultilingualTextSummarization

This project is a multilingual abstractive text summarization system I developed using the mT5 (Multilingual T5) transformer model. It generates high-quality summaries for news articles in **English**, **Hindi**, **Gujarati**, and **Bengali**, and showcases the power of cross-lingual learning in NLP.

> This summarization module will also be a key component of my **Capstone Project**, where I'm building a Legal AI system to assist judges in summarizing lengthy case documents across multiple Indian languages. This will help improve clarity and save time in courtroom decision-making processes.

## Overview

With the ever-growing volume of content in regional and global languages, I set out to build a unified summarizer that could handle multiple scripts, sentence structures, and vocabularies—all within a single model. Unlike extractive methods, this project focuses on **abstractive summarization**, where the output is generated from scratch to capture the core meaning of the input.

## Dataset

I used the **ILSUM 2.0** dataset, which consists of ~107,000 news articles and their human-written summaries across four languages.

Each sample includes:
- A news article  
- A headline  
- A manually curated abstractive summary  

🔗 Dataset source: ILSUM on HuggingFace : https://huggingface.co/datasets/ILSUM/ILSUM-2.0

## Model Architecture

The summarizer is based on the **mT5-small** model. I trained and evaluated three variants:

### 1. Fine-Tuned mT5  
Standard fine-tuning using language tags like `<en>`, `<hi>`, etc.

### 2. Prompt-Guided mT5  
Inputs are prefixed with task-specific prompts like `"summarize in hi:"` to enhance understanding in low-resource languages.

### 3. Mixed-Language mT5  
Trained on batches containing all four languages, enabling cross-lingual knowledge transfer and better generalization.

## Results

I evaluated all models using **ROUGE** metrics (ROUGE-1, ROUGE-2, ROUGE-L).

| Variant              | English | Hindi | Gujarati | Bengali |
|----------------------|---------|-------|----------|---------|
| Fine-Tuned mT5       | 42%     | 38%   | 25%      | 24%     |
| Prompt-Guided mT5    | +1–2%   | +1%   | +2–3%    | +2%     |
| Mixed-Language mT5   | **45%** | **36%** | **28%**  | **28%** |

✅ The mixed-language variant achieved the best overall performance.

##  Example Output
<img width="1744" height="163" alt="image" src="https://github.com/user-attachments/assets/c45a9d70-3aa4-43ce-8adf-f63e30cae2c7" />

