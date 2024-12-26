# Improving-Clip-Training
This project explores different approaches to enhance CLIP (Contrastive Language-Image Pre-training) training by comparing various optimizers and loss functions.
Overview
CLIP uses a dual-encoder architecture to map images and text into a shared latent space:
Image Encoder: ResNet-50 (ImageNet pretrained)
Text Encoder: DistilBERT (pretrained on BookCorpus & Wikipedia)
![image](https://github.com/user-attachments/assets/c1f3047d-a68e-4d82-ace3-af28d2ab0c59)

# Dataset
Training: 100k subset of Conceptual Captions 3M (CC3M)1
Validation:
MSCOCO validation dataset (for retrieval)
ImageNet validation dataset (for zero-shot classification)
Experiments
Optimizers Tested
AdamW (default)
Stochastic Gradient Descent (SGD)
Adam
Loss Functions Tested
CLIP Loss: Standard contrastive loss1
SogCLR Loss: Enhanced version with adaptive weighting1
CyCLIP Loss: Adds cyclic consistency constraints1
VICReg Loss: Includes variance, invariance, and covariance terms1
OnlineCLR Loss: Uses running estimates for adaptive reweighting1
# Results
Best Performing Configurations
AdamW + CyCLIP: 16.9% average performance
AdamW + SogCLR: 16.68% average performance
AdamW + CLIP: 14.81% average performance
Key Findings
AdamW consistently outperforms both SGD and Adam across all loss functions
SGD shows moderate performance only with CLIP and CyCLIP loss functions
Adam performs poorly across all loss functions
Evaluation Metrics
Performance is measured as the average of:
Image-to-Text Recall@1
Text-to-Image Recall@1
Top-1 Accuracy on classification dataset
![image](https://github.com/user-attachments/assets/0c4a323c-db92-4fec-b68b-1cebfa19b247)

