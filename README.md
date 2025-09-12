# ESCCS(Enhancing Scene Classification in Cloudy Scenarios)

Code for "Multi-Modality Transfer Learning for Cloudy Remote Sensing Images: Addressing Modality Imbalance with Knowledge Distillation"

# Abstract
In remote sensing scene classification, transfer learning is an effective strategy to address label scarcity. However, information loss and feature distribution shifts caused by cloud contamination limited the transfer of models pre-trained on cloud-free images to cloudy target images. To overcome this challenge, previous studies proposed two main solutions: removing clouds from target optical images or using Synthetic Aperture Radar (SAR) data directly in the target domain. Unfortunately, the auxiliary information cloud removal methods rely on for reconstruction may not always be available. Relying solely on SAR data discards the valuable cloud-free pixels that may still be present in optical images. Therefore, we propose a method that transfers a source model pretrained on cloud-free optical satellite images to a multi-modality target domain with cloudy optical and SAR images. A key challenge in this process is the modality imbalance issue, where the target model may overfit the superior modality while underutilizing the inferior one, thereby diminishing the complementary benefits of multimodality information. To mitigate this, we introduce a multi-step transfer strategy, which systematically quantifies the interrelationships between different modalities and enhances knowledge transfer across domains with heterogeneous data structures. Additionally, we proposed an Information Regulation Mechanism that dynamically balances the contribution of different modalities at the sample level, ensuring a more adaptive and effective learning process. Experiments on both simulated and real cloud datasets demonstrated that our proposed method outperforms state-of-the-art methods, yielding an average accuracy improvement of 13.06% in land cover scene classification.

![The framework of porposed method](images/framework.png)


# Dependency

Ubuntu18.04
CUDA11.3
PyToch1.12
python3.8

# Dataset

## SEN2MS 
Download: https://mediatum.ub.tum.de/1474000
Precessing code: https://github.com/schmitt-muc/SEN12MS
## HunanCloud
Download: The dataset will be released after the paper is published




The code will be released after the paper is published
