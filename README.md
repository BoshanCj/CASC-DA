# CASC-DA
Official implementation of **CASC-DA** for cross-scene hyperspectral image (HSI) classification under domain shift. CASC calibrates semantic structure via BAL (reweighting), SPE (margin), and IND (dependency regularization), and DualAlign aligns features (CORAL) and predictions (symmetric KL). The code will come soon.
# CASC-DA
# Class-Aware Semantic Calibration for Cross-Scene Hyperspectral Image Classification

[//]: # ( # &#40;Paper web page:[Spectral–Spatial Adversarial Multidomain Synthesis Network for Cross-Scene Hyperspectral Image Classification]&#40;https://ieeexplore.ieee.org/document/10531019&#41;.&#41;)

![CASC-DA](figure/Framwork.png)

# Abstract:
Cross-scene hyperspectral image (HSI) classification faces substantial domain shifts caused by sensor heterogeneity, acquisition variation, and scene diversity. While benchmarks provide single-pixel labels, local patches often exhibit implicit multi-label semantics due to spectral mixing and spatial overlap. This mismatch distorts prediction structure, exacerbates generalization errors, and limits the effectiveness of standard domain generalization (DG) techniques focused solely on feature or prediction invariance. We propose \textbf{Class-Aware Semantic Calibration} (CASC), a unified regularization framework that explicitly reshapes prediction behavior through three complementary principles: (i) \emph{Balance} corrects class-frequency bias via reweighted supervision; (ii) \emph{Separability} enhances boundary decision stability through margin-based logit calibration; and (iii) \emph{Independence} reduces domain-specific spurious co-occurrence via prediction-covariance decorrelation. To further improve robustness, we introduce \textbf{DualAlign}, which jointly aligns feature statistics (CORAL) and prediction distributions (symmetric KL), enforcing consistency at both representation and semantic levels. Extensive experiments on three cross-scene benchmarks (Houston, Pavia, and WHU-Hi) demonstrate that CASC-DA consistently improves performance over strong baselines, achieving an average gain of 3.0\% in overall accuracy compared with the best-performing baseline on each dataset. These results underscore the importance of semantic-structure calibration for domain-generalized HSI classification.

[//]: # (# Citation：)

[//]: # (Please cite us if our project is helpful to you!)

[//]: # (```)

[//]: # (@ARTICLE{10531019,)

[//]: # (  author={Chen, Xi and Gao, Lin and Zhang, Maojun and Chen, Chen and Yan, Shen},)

[//]: # (  journal={IEEE Transactions on Geoscience and Remote Sensing}, )

[//]: # (  title={Spectral–Spatial Adversarial Multidomain Synthesis Network for Cross-Scene Hyperspectral Image Classification}, )

[//]: # (  year={2024},)

[//]: # (  volume={62},)

[//]: # (  number={},)

[//]: # (  pages={1-16},)

[//]: # (  doi={10.1109/TGRS.2024.3401231}})

[//]: # (```)

# Requirements：
```
1. torch==1.11.0+cu113
2. python==3.8.3
3. mmcv==1.3.0
4. cupy-cuda110==8.5.0
```
# Dataset:
The dataset can be downloaded from here: [HSI datasets](https://github.com/YuxiangZhang-BIT/Data-CSHSI). We greatly appreciate their outstanding contributions.

The dataset directory should look like this:
```
datasets
  Houston
  ├── Houston13.mat
  ├── Houston13_7gt.mat
  ├── Houston18.mat
  └── Houston18_7gt.mat
```

[//]: # (# Usage:)

[//]: # (Houston datasets:)

[//]: # (```)

[//]: # (python main.py --source_name Houston13 --target_name Houston18 --patch_size 13 --training_sample_ratio 0.8)

[//]: # (```)
