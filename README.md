# HeSS: Head Sensitivity Score for Sparsity Redistribution in VGGT

### 🏆 Accepted to **CVPR 2026** 

This repository contains the official implementation of the paper **"HeSS: Head Sensitivity Score for Sparsity Redistribution in VGGT"**.

---

## 🚀 News
* **(2026.03)** Our paper has been accepted to **CVPR 2026**! 🎉
* **(Upcoming)** The calibration and inference code will be released. Stay tuned!

## 💡 Abstract
Visual Geometry Grounded Transformer (VGGT) has shown significant progress in 3D vision tasks. 
However, its global attention layers incur quadratic computational cost with respect to the number of input views, becoming a critical bottleneck for scalability.
Several sparsification-based acceleration techniques have been proposed to alleviate this issue, but they often suffer from substantial accuracy degradation.
We hypothesize that the accuracy degradation stems from the heterogeneity in head-wise sparsification sensitivity, as the existing methods apply a uniform sparsity pattern across all heads.
Motivated by this hypothesis, we present a two-stage sparsification pipeline that effectively quantifies and exploits head-wise sparsification sensitivity. 
In the first stage, we measure head-wise sparsification sensitivity using a novel metric, the Head Sensitivity Score (HeSS), which approximates the Hessian with respect to two distinct error terms on a small calibration set. In the inference stage, we perform HeSS-Guided Sparsification, leveraging the pre-computed HeSS to reallocate the total attention budget—assigning denser attention to sensitive heads and sparser attention to more robust ones.
We demonstrate that HeSS effectively captures head-wise sparsification sensitivity and empirically confirm that attention heads in the global attention layers exhibit heterogeneous sensitivity characteristics. Extensive experiments further show that our method effectively mitigates performance degradation under high sparsity, demonstrating strong robustness across varying sparsification levels.

## ✨ Key Contributions
* **HeSS metric**: We demonstrate that attention heads exhibit non-uniform sensitivity to sparsification and propose **HeSS** as a robust metric to quantify this property.
* **Hess-guided attention sparsification**: We introduce a scheme that leverages HeSS to apply differentiated sparsification, preserving sensitive heads while aggressively sparsifying robust ones.
* **Efficiency & Robustness**: Our method effectively mitigates performance degradation under high sparsity with negligible computational overhead, matching the runtime of existing sparse baselines.

## 📊 Performance at a Glance
HeSS-Guided Sparsification achieves a superior performance-efficiency trade-off on **CO3Dv2** and **DTU** datasets.
