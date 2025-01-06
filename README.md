# VLM_study
Vision Language Model study

1. Jingyi Zhang, Jiaxing Huang, Sheng Jin, Shijian Lu, Vision-Language Models for Vision Tasks: A Survey

### VLM foundation

- 10(CLIP), 17(Representation learning)

### 3.2 VLM Pre-training Objectives

- Contrastive objectives
    - 68(InfoNCE Loss)
    - 12(contrastive representeation learning)
    - 64(Image contrastive)
    - 10(Image-text contrastive)
    - 65(Image-text-label contrastive)
- Generative objectives
    - 41(Masked image modelling)
    - 14(Masked Language Modelling)
    - 42(Masked Cross-Modal Modelling)
    - 19(Image-to-Text Generation)
- Alignment objectives
    - 71, 72 중 1 (Image-Text mathcing)
    - 45, 67 중 1 (Region-Word Matching)

### 3.3 VLM Pre-training Frameworks

- Two-tower
    - 10, 17
- Two-leg
    - 19, 42 중 1
- One-tower
    - 43, 44 중 1

### 3.4.1 Zero-shot Prediction

- Image classification, Semantic Segmentation, Object Detection, Image-Text Retrieval
- pass

### 3.4.2 Linear Probing

- 평가 방식임

### 4.1 Datasets for Pre-training VLMs

- Appendix B

### 4.2 Datasets for VLM Evaluation

- Appendix C

### 5.1 VLM PRE-TRAINING with Contrastive Objectives

- 5.1.1 Image CL
    - 64(Image contrastive)
- 5.1.2 Image-Text CL
    - 112, 113, 114 중 1 (Efficient VLM pre-trainng with much less image-text pairs)
    - 18, 116 중 1 (comprehensive vision-language correlation modelling)
    - 125, 126, 127, 128 중 1 (augmenting image-text pairs)
- 5.1.3 Image-Text-Label CL
    - 65(”)

### 5.2 VLM Pre-training with Generative Objectives

- 5.2.1 Masked Image Modelling
    - 41, 70 중 1
- 5.2.2 Masked Lanuage Modelling
    - 71
- 5.2.3 Masked Cross-Modal Modelling
    - 42
- 5.2.4 Image-to-Text Generation
    - 19, 123, 83 중 1

### 5.3 VLM Pre-training with Alignment Objectives

- 5.3.1 Image-Text Matching
