## Fine-Tuning Strategies for Natural Language Inference: A Comparative Study
This project benchmarks different fine-tuning strategies for adapting pretrained language models to a downstream NLI (Natural Language Inference) classification task, comparing traditional full-parameter fine-tuning against parameter-efficient methods.
## Task & Dataset
The task is sentence-pair classification on the MultiNLI dataset, where the model predicts the inference relationship (entailment, contradiction, or neutral) between a premise and a hypothesis sentence. The dataset is publicly available on Hugging Face.
## Models

RoBERTa-large — an encoder-only model trained with a Masked Language Modeling objective, an improved variant of BERT trained on more data for longer
LLaMA 3 8B — a decoder-only large language model pretrained on roughly 15 trillion tokens

## Methods Compared

Full Fine-Tuning — updating all model parameters on the downstream task, used as the baseline
LoRA (Low-Rank Adaptation) — injects small trainable low-rank matrices instead of updating all weights
P-Tuning — a soft-prompting approach that learns continuous prompt embeddings rather than modifying the model's core weights

For each method: model architecture, hyperparameters, training time, number of trainable parameters, and final accuracy are reported and compared.
## Background: Prompting Approaches

Hard Prompting — fixed, human-readable natural language prompts, no parameter updates
Soft Prompting — learned continuous prompt embeddings while the base model stays frozen

## Goal
Comparing full fine-tuning, LoRA, and P-Tuning across an encoder model (RoBERTa-large) and a decoder-based LLM (LLaMA 3 8B) to explore trade-offs between training cost, parameter efficiency, and task performance.
