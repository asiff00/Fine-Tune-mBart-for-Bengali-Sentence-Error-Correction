# Fine-Tuning mBart for Bengali Sentence Error Correction

[![Training Notebook](https://img.shields.io/badge/View-Training%20Notebook-blue?style=flat-square&logo=Jupyter)](finetune.ipynb)
[![Hugging Face Demo](https://img.shields.io/badge/Try-Hugging%20Face%20Demo-brightgreen?style=flat-square&logo=huggingface)](https://huggingface.co/spaces/asif00/Bengali_Sentence_Error_Correction__mbart_bn_error_correction)
[![Fine-Tuned Model](https://img.shields.io/badge/Fine--Tuned%20Model-Repository-red?style=flat-square&logo=github)](https://github.com/himisir/Bengali-Sentence-Error-Correction)



## Overview

Fine-tuning the mBart model to correct grammatical and syntactical errors in Bengali sentences. The aim is to achieve high accuracy in transforming incorrect sentences into their correct form. The full training process can be found here: [Notebook](finetune.ipynb) Here is a live [HuggingFace Demo](https://huggingface.co/spaces/asif00/Bengali_Sentence_Error_Correction__mbart_bn_error_correction) of the finetune model in action. 

### Base Model

- **Model**: [mBART Large 50](https://huggingface.co/facebook/mbart-large-50)
  - **Description**: A multilingual transformer model capable of understanding and generating 50 different languages.

### Dataset

- **Source**: [BNSEC Data Repository](https://github.com/hishab-nlp/BNSECData)
  - **Size**: 1.3 Million sentence pairs
  - **Characteristics**: Contains a mix of correct and grammatically incorrect Bengali sentences.

## Training Specifications

```yaml
Optimizer: AdamW
Learning Rate: 0.00001
Batch Size: 128
Training Steps: 6500
GPU: Google Colab A100
Epochs: 1
Max Token Length: 32
```

## Model Performance Metrics

| Metric | Training | Post-Training Testing |
| ------ | -------- | --------------------- |
| BLEU   | 0.805    | 0.443                 |
| CER    | 0.053    | 0.159                 |
| WER    | 0.101    | 0.406                 |
| Meteor | 0.904    | 0.655                 |
