# Thesis Project: Multimodal Harmful Content Detection

This repository contains the implementation, experimental setup, and documentation for the Master's thesis on **Multimodal Deep Learning for Harmful Video Content Detection**.

## Repository Structure

```
/src
  /data        # Data loading, preprocessing, augmentation
  /preproc     # Data processing
  /models      # Baseline and proposed models (BERT, ResNet, fusion mechanisms)
README.md
requirements.txt
LICENSE
```

## Workflow

1. **Data Preparation**
   - Collect datasets (e.g., Hateful Memes).
   - Preprocess:
     - Extract frames (e.g., 1 fps).
     - Extract audio features with librosa.
     - Transcribe speech with Whisper ASR.
   - Store splits (train/val/test) with fixed seed for reproducibility.

2. **Model Implementation**
   - Baseline: text-only (BERT), image-only (ResNet/ViT), audio-only (wav2vec).
   - Proposed: multimodal fusion models.
     - Early Fusion (concatenation).
     - Attention-based Fusion (transformer encoder).

3. **Training**
   - Optimizer: Adam with weight decay.
   - Learning rate: 1e-4 (fusion), 2e-5 (encoders).
   - Regularization: dropout (0.3–0.5), gradient clipping.
   - Early stopping based on validation F1 or AUROC.

## Ethical Considerations

- Respect dataset licenses and platform ToS.
- Ensure PII anonymization in any collected data.
- Provide annotator guidelines and mental health resources.
- Audit models for bias and fairness across subgroups.

---

**Author:** Nguyen Viet Hoang  
**Thesis:** MSc Data Science, LJMU  

