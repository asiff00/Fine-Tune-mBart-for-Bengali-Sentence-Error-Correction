# Fine-Tuning mBart for Bengali Sentence Error Correction

## Overview

Fine-tuning the mBart model to correct grammatical and syntactical errors in Bengali sentences. The aim is to achieve high accuracy in transforming incorrect sentences into their correct form. Full training process can be found here: [Notebook](finetune.ipynb)

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
| Meteor | 0.904    | 0.6                   |
