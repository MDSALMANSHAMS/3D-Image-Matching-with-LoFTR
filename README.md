# 3D-Image-Matching-with-LoFTR

![alt text](https://github.com/zju3dv/LoFTR/blob/master/assets/loftr-github-demo.gif)

### Paper
LoFTR: Detector-Free Local Feature Matching with Transformers
Jiaming Sun*, Zehong Shen*, Yu'ang Wang*, Hujun Bao, Xiaowei Zhou
CVPR 2021

## Introduction
LoFTR stand for Detector-Free Local Feature Matching with Transformers.

 <img width="842" alt="pipeline" src="https://github.com/MDSALMANSHAMS/3D-Image-Matching-with-LoFTR/assets/68110323/6edb7862-e9b9-4577-870a-50bf4d318fdc">

### LoFTR has four components:
1. A local feature CNN extracts the coarse-level feature maps F(A) and F(B), together with the fine-level feature maps F(A) and F(B) from the image pair I(A) and I(B).
2. The coarse feature maps are flattened to 1-D vectors and added with the positional encoding. The added features are then processed by the Local Feature TRansformer (LoFTR) module, which has N(c) self-attention and cross-attention layers.
3. A differentiable matching layer is used to match the transformed features, which ends up with a confidence matrix P(c). The matches in P(c) are selected according to the confidence threshold and mutual-nearest-neighbor criteria, yielding the coarse-level match prediction M(c).
4. For every selected coarse prediction (i, j) E M(c), a local window with size (w x w) is cropped from the fine-level feature map. Coarse matches will be refined within this local window to a sub-pixel level as the final match prediction M(f).
