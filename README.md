# Comparative Analysis of Segmentation Models on Human Visual Diet Dataset

This project compares the performance and interpretability of three deep learning models — ResNet-18, DenseNet-121, and SegFormer (a Vision Transformer) — for semantic segmentation on the Human Visual Diet dataset, a benchmark designed to reflect human-like visual experience.
                                                          
##  Motivation

While CNNs have driven significant progress in vision tasks, they often rely on superficial features and struggle with generalization. This project investigates:

- Can architectures like Vision Transformers perform better on complex, context-rich scenes?
- Do Grad-CAM (for CNNs) and attention maps (for ViTs) show human-aligned reasoning?
- What challenges do models face when trained on more "human-like" data?


##  Models

- `ResNet-18` and `DenseNet-121` are used with custom decoder heads for segmentation.
- `SegFormer-B0` (from HuggingFace) is fine-tuned for semantic segmentation.

##  Dataset 

The Human Visual Diet (HVD) dataset has been entirely created by Madan et al. (2024) and is available in their github page: https://github.com/Spandan-Madan/human_visual_diet.

##  Metrics

- **Pixel Accuracy**
- **Mean IoU**  
- Visualizations via:
  - Grad-CAM (ResNet, DenseNet)
  - Self-attention maps (SegFormer ViT)

##  Key Results

| Model       | Pixel Acc. | Mean IoU |
|-------------|------------|----------|
| ResNet-18   | ~57%       | ~0.35    |
| DenseNet-121| ~72%       | ~0.50    |
| SegFormer-B0| ~81%       | ~0.60    |

- All models struggle with **edge segmentation**, confuse **floor/wall**, and sometimes rely on **contextual shortcuts**.
- ViT attention maps show more global reasoning, but often attend to irrelevant regions too.

## Author 

Francesco Plastina 

Undergraduate Student Harvard University 

Course: Neuro 140/240
