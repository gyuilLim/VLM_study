### VLM foundation

- ~~**CLIP(10)** : Learning transferable visual models from natural language supervision(2021)~~
    - **non-linear projection** : Bachman et al.(2019), Chen et al. (2020b)
    - **Gradient checkpointing**  : Griewank & Walther, 2000; Chen et al., 2016
    - **half-precision Adam statistics** : Dhariwalet al., 2020
- **Representation learning(17)** : Scaling up visual and vision-language representation learning with noisy text supervision(2021)

### 3.2 VLM Pre-training Objectives

- Contrastive objectives
    - ~~**InfoNCE Loss(68)** : Representation learning with contrastive predictive coding(2018)~~
    - ~~**NCE Loss(68)** : Noise-contrastive estimation: A new estimation principle for unnormalized statistical models(2010)~~
    - **contrastive representeation learning**
        - **12** : Momentum contrast for unsupervised visual repre-sentation learning(2020)
    - **Image contrastive**
        - **64** : Self-supervision meets language-image pretraining(2022)
    - **Image-text contrastive**
        - ~~**10** : CLIP~~
    - **Image-text-label contrastive**
        - **65** : Unified contrastive learning in image-text-label space(2022)
- Generative objectives
    - **Masked image modelling**
        - **41** : Masked autoencoders are scalable vision learners(2022)
    - **Masked Language Modelling**
        - **14** : Bert: Pre-training of deep bidirectional transformers for language understanding(2018)
    - **Masked Cross-Modal Modelling**
        - **42** : Flava: A foundational language and vision alignment model(2022)
    - **Image-to-Text Generation**
        - **19** : Coca: Contrastive captioners are image-text foundation
        models(2022)
- Alignment objectives
    - **Image-Text mathcing(중 1)**
        - **71** : Coarse-to-fine vision-language pre-training with fusion in the backbone.
        - **72** : Vlmo: Unified vision-language pre-training with mixture-of-modality-experts(2021)
    - **Region-Word Matching(중 1)**
        - **45** : Detclip: Dictionary-enriched visual-concept paralleled pre-training for open-world detection
        - **67** : Grounded language-image pre-training(2022)

### 3.3 VLM Pre-training Frameworks

- **Two-tower**
    - **~~CLIP(10)~~**
    - ~~**17** : Scaling up visual and vision-language representation learning with noisy text supervision(2021)~~
- **Two-leg(중 1)**
    - ~~**19** : Coca: Contrastive captioners are image-text foundation models(2022)~~
    - ~~**42 :** Flava: A foundational language and vision alignment model(2022)~~
- **One-tower(중 1)**
    - **43** : Image-and-language understanding from pixels only(2022)
    - **44** :  Unifying vision-language representation space with single-tower transformer(2023)

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
    - ~~**Image contrastive(64)** : Slip: Self-supervision meets language-image pre-training(2022)~~
- 5.1.2 Image-Text CL
    - **Efficient VLM pre-trainng with much less image-text pairs(중 1)**
        - **112** : Data efficient language-supervised zero-shot recognition with optimal transport distillation(2021)
        - **113** : Supervision exists everywhere: A data efficient contrastive language-image pre-training paradigm(2021)
        - **114** : Contrastive vision-language pre-training with limited resources(2022)
    - **comprehensive vision-language correlation modelling(중 1)**
        - **18** : Filip: Fine-grained interactive language-image pretraining(2021)
        - **116** : Pyramidclip: Hierarchical feature alignment for vision-language model pretraining(2022)
    - **augmenting image-text pairs(중 1)**
        - **125** : Ra-clip: Retrieval augmented contrastive language-image pre-training(2023)
        - **126** : Improving clip training with language rewrites(2023)
        - **127** :  Alip: Adaptive language-image pre-training with synthetic caption(2023)
        - **128** : Growclip: Data-aware automatic model growing for large-scale contrastive language-image pre-training(2023)
- 5.1.3 Image-Text-Label CL
    - **~~65~~**

### 5.2 VLM Pre-training with Generative Objectives

- 5.2.1 Masked Image Modelling(중 1)
    - **~~41~~**
    - **70** : Beit: Bert pre-training of image transformers(2021)
- 5.2.2 Masked Lanuage Modelling
    - ~~**71** : Coarse-to-fine vision-language pre-training with fusion in the backbone~~
- 5.2.3 Masked Cross-Modal Modelling
    - **~~42~~**
- 5.2.4 Image-to-Text Generation
    - ~~**19** : Coca: Contrastive captioners are image-text foundation models(2022)~~
    - **123** : Nlip: Noise-robust language-image pre-training(2022)
    - **83** : Pali: A jointly-scaled multilingual language-image model(2022)

### 5.3 VLM Pre-training with Alignment Objectives

- 5.3.1 Image-Text Matching(중 1)
    - **~~42~~**
    - **~~71~~**
    - ~~**72** : Vlmo: Unified vision-language pre-training with mixture-of-modality-experts(2021)~~
- 5.3.2 Region-Word Matching(중 1)
    - ~~**67** : Grounded language-image pre-training(2022)~~
    - ~~**71** : Coarse-to-fine vision-language pre-training with fusion in the backbone~~
    - ~~**45** : Detclip: Dictionary-enriched visual-concept paralleled pre-training for open-world detection~~

### 6 VLM Transfer learning

- 6.3.1 Transfer via prompt tuning
    - Transfer with Text Prompt Tuning
        - **31(CoOp)** : Learning to prompt for vision-language models(2022)
    - Transfer with Visual Prompt Tuning(중 1)
        - **148** : Retrieval-enhanced visual prompt learning for few-shot classification(2023)
        - **166** : Visual prompt tuning(2022)
    - Transfer with Text-Visual Prompt Tuning
        - **149(UPT)** : Unified vision and language prompt learning(2022)
- 6.3.2 Transfer via Feature Adaptation
    - **33(Clip-adapter)** : Clip-adapter: Better vision-language models with feature adapters(2021)
- 6.3.3 Other Transfer Methods
    - pass

### 7. VLM Knowledge Distillation

- 7.1 Motivation of Distilling Knowledge from VLMs
    - **174(clip to segmentation)** : Towards adapting clip for zero-shot
    semantic segmentation(2022)
- 7.2.1 Knowledge Distillation for Object Detection
    - **36(ViLD, object detection knowledge distillation)** : Open-vocabulary object detection via vision and language knowledge distillation(2021)
    - **추후 관심있으면 더 읽기 189(PB-OVD)** : Open vocabulary object detection with pseudo bounding-box labels(2022)
- 7.2.2 Knowledge Distillation for semantic segmentation
    - **35** : Decoupling zero-shot semantic segmentation(2022)
    - **175(CLIPseg)** : Image segmentation using text and image prompts(2022)
