# Under-Review-EIA-CKD-ECG
# EIA-CKD: End-to-End Internal Augmentation and Curriculum-Based Knowledge Distillation for Lightweight ECG Classification
Official implementation of EIA-CKD, a lightweight end-to-end framework for ECG classification using internal multi-view augmentation and curriculum-based knowledge distillation.

## Overview

Automated ECG classification is important for wearable and resource-constrained
healthcare applications, where high diagnostic performance must be achieved with
limited computational and memory resources.

We propose **EIA-CKD (End-to-End Internal Augmentation and Curriculum-Based
Knowledge Distillation)**, a lightweight framework that performs knowledge
distillation within a single network without requiring a separately pre-trained
teacher model.

During training, multiple views are internally generated from each ECG image
and processed through a shared lightweight CNN backbone. The resulting predictions
are aggregated by an attention-based consensus module to generate an internal
supervisory signal. A curriculum-based optimization strategy gradually increases
the contribution of this internal knowledge during training.

The backbone combines **depthwise separable convolutions**, residual learning,
and **Convolutional Block Attention Modules (CBAM)** to achieve a low computational
footprint while maintaining competitive classification performance.

The proposed framework was evaluated on the **PTB-XL** and **Chapman** ECG datasets.
With approximately **102K trainable parameters**, EIA-CKD achieves:

| Dataset | Accuracy | AUROC |
|---------|----------|-------|
| PTB-XL | 84.67% | 95.60% |
| Chapman | 94.23% | 99.16% |

These results demonstrate the potential of EIA-CKD for efficient ECG classification
in wearable and resource-constrained IoMT applications.
<p align="center">
  <img src="assets/eia_ckd_framework.png"
       alt="EIA-CKD Framework"
       width="900">
</p>
