# Bert2GPT Indonesian Text Summarizer
This repository hosts a sequence-to-sequence model that employs BERT for encoding and GPT for decoding, crafted specifically for the task of text summarization. The model is optimized for the Indonesian language, having been fine-tuned on the 'id_liputan6' dataset. This dataset is comprised of text summarization data derived from Liputan6, a prominent Indonesian news website. The ultimate goal of this project is to deliver succinct and accurate summaries of Indonesian news articles.

---

## Table of Contents
- [Introduction](#introduction)
- [Dataset](#dataset)
- [Methodology](#methodology)
- [Results](#results)
- [Room For Improvement](#room-for-improvement)
- [References](#references)
- [Attachment](#attachment)

---
# Introduction

The Bert2GPT Indonesian Text Summarizer is a sequence-to-sequence model that combines the encoding capabilities of BERT with the decoding prowess of GPT, specifically designed for the task of text summarization within the Indonesian context. This model addresses the growing need for efficient information processing in the face of increasing digital content, particularly in news media.

Indonesia's diverse linguistic landscape and the proliferation of digital news platforms necessitate advanced tools for content comprehension. The Bert2GPT Indonesian Text Summarizer caters to this need by providing a mechanism to distill lengthy news articles into their essential summaries, thus aiding in rapid information assimilation.

Housed in this repository is a model meticulously fine-tuned on the 'id_liputan6' dataset, which comprises text summarization pairs sourced from Liputan6, one of Indonesia's prominent news websites. This choice of dataset ensures that the model is well-adapted to the Indonesian language's syntactic and semantic nuances, as well as the stylistic characteristics typical of local news reporting.

The primary objective of the Bert2GPT Indonesian Text Summarizer is to enhance the accessibility of news content by generating concise and coherent summaries. This endeavor aligns with the broader goal of leveraging AI to bridge the gap between vast information streams and the end-user's need for quick and reliable insights. Through this project, we aim to contribute to the domain of natural language processing by offering a tool that not only streamlines content consumption but also fosters a better-informed and engaged audience in the Indonesian digital ecosystem.

---
# Finetuning Corpus
This model is fine-tuned using the [id_liputan6](https://huggingface.co/datasets/id_liputan6) dataset, based on the [cahya/bert-base-indonesian-1.5G and cahya/gpt2-small-indonesian-522M](https://huggingface.co/cahya), both developed by Cahya.

# Usage
Google Colab: https://colab.research.google.com/drive/1x1l6m5rKQGUszmX3CkqHf9tpvKvMkpzB?usp=sharing
