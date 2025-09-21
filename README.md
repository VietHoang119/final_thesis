# Thesis Project: Multimodal Harmful Content Detection

This repository contains the implementation, experimental setup, and documentation for the Master's thesis on **Multimodal Deep Learning for Harmful Video Content Detection**.

## Repository Structure

```
/src
  /data        # Data loading, preprocessing, augmentation
  /preproc     # Data processing
  /models      # Baseline and proposed models (BERT, ResNet, fusion mechanisms)
  /train       # Training loops, schedulers, logging
  /eval        # Evaluation metrics
  /configs     # YAML/JSON configuration files for experiments
  /figures     # Auto-generated plots, visualizations (Grad-CAM, attention heatmaps)
  /tables      # CSV results for performance tables
/docs
  Thesis_Ch4to6_Skeleton.docx  # Word skeleton for chapters 4-6
  Thesis_Ch4to6_Skeleton.tex   # LaTeX skeleton for chapters 4-6
README.md
requirements.txt
LICENSE
```

## Workflow

1. **Data Preparation**
   - Collect datasets (e.g., Hateful Memes).
   - Preprocess:
     - Extract frames with OpenCV (e.g., 1 fps).
     - Extract audio features with librosa (MFCC, mel).
     - Transcribe speech with Whisper ASR.
   - Store splits (train/val/test) with fixed seed for reproducibility.

2. **Model Implementation**
   - Baseline: text-only (BERT), image-only (ResNet/ViT), audio-only (wav2vec or CNN).
   - Proposed: multimodal fusion models.
     - Early Fusion (concatenation).
     - Attention-based Fusion (transformer encoder).

3. **Training**
   - Optimizer: Adam with weight decay.
   - Learning rate: 1e-4 (fusion), 2e-5 (encoders).
   - Regularization: dropout (0.3–0.5), gradient clipping.
   - Early stopping based on validation F1 or AUROC.

4. **Evaluation**
   - Metrics: Accuracy, Precision, Recall, F1 (macro & class-wise), AUROC, AUPRC.
   - Generate confusion matrices, ROC/PR curves, ablation results.
   - Interpretability: Grad-CAM (visual), attention weights (text/audio).

5. **Documentation**
   - Chapter 4: Implementation & Experimental Setup.
   - Chapter 5: Results & Discussion.
   - Chapter 6: Conclusion & Future Work.
   - Fill in skeleton docs with tables, figures, and analysis.

## Requirements

- Python 3.10+
- PyTorch 2.x
- Hugging Face Transformers, Datasets
- torchvision
- OpenCV
- librosa
- FFmpeg
- scikit-learn
- matplotlib, seaborn (for visualization)

Install via:

```bash
pip install -r requirements.txt
```

## Ethical Considerations

- Respect dataset licenses and platform ToS.
- Ensure PII anonymization in any collected data.
- Provide annotator guidelines and mental health resources.
- Audit models for bias and fairness across subgroups.

---

**Author:** Nguyen Viet Hoang  
**Thesis:** MSc Data Science, LJMU  

