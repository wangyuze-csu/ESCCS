# ESCCS(Enhancing Scene Classification in Cloudy Scenarios)

Code for "Multi-Modality Transfer Learning for Cloudy Remote Sensing Images: Addressing Modality Imbalance with Knowledge Distillation"

# Abstract
In remote sensing scene classification, transfer learning is an effective strategy to address label scarcity. However, information loss and feature distribution shifts caused by cloud contamination limited the transfer of models pre-trained on cloud-free images to cloudy target images. To overcome this challenge, previous studies proposed two main solutions: removing clouds from target optical images or using Synthetic Aperture Radar (SAR) data directly in the target domain. Unfortunately, the auxiliary information cloud removal methods rely on for reconstruction may not always be available. Relying solely on SAR data discards the valuable cloud-free pixels that may still be present in optical images. Therefore, we propose a method that transfers a source model pretrained on cloud-free optical satellite images to a multi-modality target domain with cloudy optical and SAR images. A key challenge in this process is the modality imbalance issue, where the target model may overfit the superior modality while underutilizing the inferior one, thereby diminishing the complementary benefits of multimodality information. To mitigate this, we introduce a multi-step transfer strategy, which systematically quantifies the interrelationships between different modalities and enhances knowledge transfer across domains with heterogeneous data structures. Additionally, we proposed an Information Regulation Mechanism that dynamically balances the contribution of different modalities at the sample level, ensuring a more adaptive and effective learning process. Experiments on both simulated and real cloud datasets demonstrated that our proposed method outperforms state-of-the-art methods, yielding an average accuracy improvement of 13.06% in land cover scene classification.

![The framework of proposed method](images/Fig.2.jpg)

# Dependency

Ubuntu18.04
CUDA11.3
PyToch1.12
python3.8

# Dataset

## SEN2MS 
Download(Source): https://mediatum.ub.tum.de/1474000
Precessing code: https://github.com/schmitt-muc/SEN12MS
The cloud masks will be provided upon request. 
![Example of each category in SEN12MS Cloud dataset](images/Fig.5.jpg)

## HunanCloud
Download: The dataset will be released after the paper is published
![Example of each category in Hunan Cloud dataset](images/Fig.6.jpg)
# Reference

## Filtering and Generation of Pseudo-Labels
In the first step of the multi-step transfer process, the source-domain model guides the auxiliary model for knowledge transfer. To ensure the reliability of the auxiliary model, we perform filtering based on the logit outputs during pseudo-label generation. This helps mitigate the effect of excessive noise and improves the stability of the learning process. For the detailed procedure, please refer to: Cross-Sensor Remote-Sensing Images Scene Understanding Based on Transfer Learning Between Heterogeneous Networks. https://ieeexplore.ieee.org/abstract/document/9570728。


In the second step of the multi-step transfer process, we did not apply filtering in order to preserve the model’s ability to repeatedly learn multi-modal balance under complex cloud-covered conditions. This choice was made because heavily cloud-contaminated samples might otherwise be incorrectly discarded as noise.

Our overall pseudo-label generation technique was inspired by Knowledge Distillation Zoo (https://github.com/AberHu/Knowledge-Distillation-Zoo).


# Compared method:

## Opt to Opt

SPL： Thick cloud removal in optical remote sensing images using a texture complexity guided self-paced learning method. reference(https://github.com/GeoX-Lab/TPL)  
KD-S (soft Knowledge Distillation): Knowledge distillation and student-teacher learning for visual intelligence: A review and new outlooks reference(https://github.com/AberHu/Knowledge-Distillation-Zoo)

## Opt to SAR
TTL: A general transitive transfer learning framework for cross-optical sensor remote sensing image scene understanding.  
CycIT: Two-stage cross-modality transfer learning method for military-civilian SAR ship recognition(Reproduced by ourselves, will be released after the paper is published)  

## Opt to Opt&SAR
KDHN: Cross-Sensor Remote-Sensing Images Scene Understanding Based on Transfer Learning Between Heterogeneous Networks(https://ieeexplore.ieee.org/abstract/document/9570728)  
TLF: A comparative review on multi-modal sensors fusion based on deep learning（Reproduced by ourselves, will be released after the paper is published）  


The code will be released after the paper is published  
