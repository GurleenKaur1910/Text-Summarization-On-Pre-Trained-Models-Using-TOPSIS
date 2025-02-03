# Text-Summarization-On-Pre-Trained-Models-Using-TOPSIS

## Overview
This project applies the TOPSIS (Technique for Order of Preference by Similarity to Ideal Solution) method to rank various pre-trained NLP models for text summarization. The goal is to identify the most balanced model considering both summarization quality (ROUGE scores) and inference efficiency (inference time).

## Models Evaluated
The following pre-trained NLP models were evaluated in this project for their text summarization capabilities:

facebook/bart-large-cnn
t5-small
google/pegasus-xsum
facebook/bart-large-xsum
google/pegasus-large

## Performance Metrics
The models were ranked based on the following metrics:

ROUGE-1 (+): Higher ROUGE-1 score is better.

ROUGE-2 (+): Higher ROUGE-2 score is better.

ROUGE-L (+): Higher ROUGE-L score is better.

Inference Time (ms) (-): Lower inference time is better.

Model Size (MB) (-): Smaller model size is better.

Note:
(+) indicates benefit criteria (higher values are better).
(-) indicates cost criteria (lower values are better).

## Methodology
1. Data Normalization
Each metric was normalized using vector normalization to standardize the results across models with varying ranges.

2. Weight Assignment
We assigned weights to the metrics based on their importance in evaluating the models:

ROUGE-1: 35%
ROUGE-2: 30%
ROUGE-L: 20%
Inference Time: 15%

3. Ideal Best & Worst Values
The ideal best and worst values for each metric were determined based on the normalized data. The best value represents the highest performance (for ROUGE scores) and the lowest for cost criteria (inference time and model size).

4. TOPSIS Score Calculation
The TOPSIS score for each model was calculated by computing the Euclidean distance from both the ideal best and worst values. The model with the highest TOPSIS score represents the best-performing model.

## Results
The final TOPSIS scores and rankings are stored in the file topsis_summarization_ranking.csv.

Below is a summary of the TOPSIS rankings:
DistilBERT emerges as the best model for text summarization, offering the best balance between ROUGE scores and efficiency (inference time).
ALBERT performs very well in ROUGE scores, but it is slightly outpaced by DistilBERT's better inference time.
BERT and RoBERTa have strong ROUGE scores but suffer from larger model sizes and longer inference times, which affect their rankings.
XLNet ranks the lowest due to its large model size and high inference time, despite decent ROUGE scores.
