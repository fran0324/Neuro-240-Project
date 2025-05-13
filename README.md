# Semantic Segmentation with CNNs and Vision Transformers on the Human Visual Diet Dataset

This project compares the performance and interpretability of three deep learning models — ResNet-18, DenseNet-121, and SegFormer (a Vision Transformer) — for semantic segmentation on the Human Visual Diet dataset, a benchmark designed to reflect human-like visual experience.

##  Motivation

While CNNs have driven significant progress in vision tasks, they often rely on superficial features and struggle with generalization. This project investigates:

- Can architectures like Vision Transformers perform better on complex, context-rich scenes?
- Do Grad-CAM (for CNNs) and attention maps (for ViTs) show human-aligned reasoning?
- What challenges do models face when trained on more "human-like" data?

##  Project Structure
├── models/
│ ├── resnet_segmentation.py
│ ├── densenet_segmentation.py
│ └── vit_segformer.py
├── utils/
│ ├── gradcam.py
│ ├── attention_visualization.py
│ └── data_loader.py
├── notebooks/
│ ├── ResNet.ipynb
│ ├── DenseNet-2.ipynb
│ └── Copy_of_miniViT.ipynb
├── results/
│ ├── predictions/
│ └── visualizations/
├── main.py
├── requirements.txt
└── README.md


## 🧪 Models

- `ResNet-18` and `DenseNet-121` are used with custom decoder heads for segmentation.
- `SegFormer-B0` (from HuggingFace) is fine-tuned for semantic segmentation.

## 📊 Metrics

- **Pixel Accuracy**
- **Mean IoU**  
- Visualizations via:
  - Grad-CAM (ResNet, DenseNet)
  - Self-attention maps (SegFormer ViT)

## 📈 Key Results

| Model       | Pixel Acc. | Mean IoU |
|-------------|------------|----------|
| ResNet-18   | ~57%       | ~0.35    |
| DenseNet-121| ~72%       | ~0.50    |
| SegFormer-B0| ~81%       | ~0.60    |

- All models struggle with **edge segmentation**, confuse **floor/wall**, and sometimes rely on **contextual shortcuts**.
- ViT attention maps show more global reasoning, but often attend to irrelevant regions too.


