# visual-reasoning-pipeline
End-to-end experiments with vision model: segmentation (SAM), detection (OWL-ViT), diffusion generation, and fine-tuning a Visual Language Model.

# Project Overview

Recent advances in multimodal AI have enabled models to understand and generate images through prompts. Unlike traditional computer vision systems, modern vision models can be controlled through:

- Natural language prompts
- Bounding box coordinates
- Pixel-level segmentation masks
- Hyperparameter tuning

This repository implements a set of experiments using state-of-the-art vision models including:

- **Segment Anything Model (SAM)** – universal image segmentation
- **OWL-ViT** – zero-shot object detection
- **Stable Diffusion** – generative image models
- **DreamBooth** – diffusion model fine-tuning

The project explores how these models can be combined into **interactive visual AI workflows**.

---

# Key Features

## Image Segmentation

Using **Meta’s Segment Anything Model (SAM)** to generate segmentation masks with different prompting strategies.

Prompting methods include:

- Positive pixel coordinates
- Negative pixel coordinates
- Bounding box prompts

This allows fine-grained control over which regions of an image should be segmented.

---

## Object Detection

Zero-shot object detection using **OWL-ViT**.

The model is prompted using **natural language queries**, enabling detection of arbitrary objects without task-specific training.

Example:
Prompt: "construction worker helmet"


The model returns bounding boxes corresponding to relevant objects.

---

## Image Generation

Image generation with **Stable Diffusion 2.0**.

Prompt control includes:

- Guidance scale
- Number of inference steps
- Strength parameters

These hyperparameters influence image quality, diversity, and prompt adherence.

---

## Image In-Painting

In-painting combines:

- Object detection
- Image segmentation
- Diffusion-based generation

Workflow:

1. Detect an object using OWL-ViT
2. Segment the object using SAM
3. Replace it using Stable Diffusion

This enables **semantic image editing**.

---

## Fine-Tuning with DreamBooth

DreamBooth is used to fine-tune Stable Diffusion to generate **personalized images**.

The fine-tuned model learns to associate a custom token with a specific subject.

Example:
"a photo of sks_person riding a bicycle"


The model generates images of the specific subject in new contexts.

---

## Experiment Tracking

Prompt engineering is an iterative process.

Experiments are tracked using **Comet ML**, allowing:

- prompt comparison
- hyperparameter tracking
- reproducible experiments

This enables systematic optimization of prompting workflows.

---

# Technologies Used

- Python
- PyTorch
- Hugging Face
- Stable Diffusion
- Segment Anything Model (SAM)
- OWL-ViT
- DreamBooth
- Comet ML

---

# Vision Models Used

| Model | Task |
|-----|-----|
| SAM | Image segmentation |
| OWL-ViT | Zero-shot object detection |
| Stable Diffusion 2.0 | Image generation |
| DreamBooth | Diffusion model fine-tuning |

---

# Key Learnings

Through this project I explored:

- Prompt engineering for multimodal models
- Controlling vision models through coordinates, masks, and text
- Diffusion model hyperparameter tuning
- Personalizing generative models through DreamBooth
- Building reproducible experimentation workflows
