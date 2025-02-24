# Internal Compass: Zooming Zero-Shot Image Classification with Internal Confidence

This repository contains the code for **Internal Compass**, a research project exploring zero-shot image classification using internal confidence scores from Vision-Language Models (VLMs). The work builds on mechanistic interpretability techniques to analyze internal representations of VLMs, improving zero-shot classification performance.

## Features
- Zero-shot image classification using Vision-Language Models.
- Internal confidence-based classification using **Logit Lens**.
- Support for **InstructBLIP** and **LLaVA** models.
- Tested on **CIFAR-10** dataset.

---

## Setup

### Files
```
git clone https://github.com/ansh997/incom.git
cd vl-interp
```

### Environment

```
# Create a new conda environment
conda create -n vl python=3.9 -y
conda activate vl

# install from root repo first
pip3 install -e .

# Set up LLaVA repo
cd src/caption/llava/LLaVA
pip3 install -e .

# Install some remaining packages
pip3 install lightning openai-clip transformers==4.37.2 omegaconf python-dotenv "numpy<2"

# Missing dependency (Only works with Conda not pip)
conda install conda-forge::pattern -y
```

### Model Weights

The configs for InstructBLIP models are under `src/caption/lavis/configs/`.

In order to get InstructBLIP (7B) working, you should download the [pretrained model weights](https://storage.googleapis.com/sfr-vision-language-research/LAVIS/models/InstructBLIP/instruct_blip_vicuna7b_trimmed.pth) and [vicuna7b weights](https://huggingface.co/lmsys/vicuna-7b-v1.1).

## 📊 Results

We tested the method on **CIFAR-10** and compared it with standard models:

| **Method**                 | **Accuracy (%)** |
|----------------------------|-----------------|
| EfficientNet (Supervised)  | 89.32%          |
| ResNet18 (Supervised)     | 90.89%          |
| ViT (Supervised)          | 96.70%          |
| SimCLR (One-Shot)        | 93.20%          |
| CLIP (Zero-Shot)         | 95.10%          |
| SigLIP (Zero-Shot)       | 95.32%          |
| **Our Method (Zero-Shot)** | 82.31%          |




```
@misc{pal2024internalcompass,
  title={Internal Compass: Zooming Zero-Shot Image Classification with Internal Confidence},
  author={Himanshu Pal, Snigdha Agarwal, Uday Bhaskar},
  institution={IIIT Hyderabad},
  year={2024}
}
```

