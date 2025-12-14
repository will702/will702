# PlastiTrace

AI-powered plastic-type detection system using CNN transfer learning for mobile deployment.

## Overview

PlastiTrace is a computer vision system that classifies plastic types (HDPE, PET, PP, PS) from images using deep learning. The model achieves >99% validation accuracy via ResNet50 transfer learning and is optimized for offline mobile inference through ONNX export. Built for the AI for Sustainability Hackathon, where it received Highly Commended / Top Finalist recognition.

## Problem & Motivation

Manual plastic sorting is error-prone and limits recycling efficiency. Automated classification can improve sorting accuracy, reduce contamination, and enable consumer education through mobile applications. The challenge requires high accuracy, real-time inference, and offline capability for field deployment.

## Architecture

The system consists of three main components:

1. **Training Pipeline**: PyTorch-based training with ResNet50 transfer learning, custom dataset curation, and validation workflows
2. **Model Export**: ONNX conversion for cross-platform deployment, with TensorFlow Lite compatibility for mobile optimization
3. **Mobile Inference**: React Native application with on-device model execution, camera integration, and educational UI

Data flows from image capture → preprocessing → model inference → classification output → user feedback and educational content.

## Key Technical Decisions

- **ResNet50 Transfer Learning**: Leveraged pre-trained ImageNet weights to achieve >99% accuracy with limited training data
- **ONNX Export**: Chose ONNX for cross-platform compatibility and efficient mobile inference without cloud dependencies
- **Mobile-First Design**: Prioritized offline inference to enable field use without network connectivity
- **Scientific Documentation**: Produced LaTeX reports with PGFPlots and ablation studies to validate model performance

## Setup & Usage

### Training

```bash
# Install dependencies
pip install torch torchvision onnx

# Train model
python train.py --model resnet50 --epochs 50

# Export to ONNX
python export_onnx.py --checkpoint best_model.pth
```

### Mobile Deployment

```bash
# React Native setup
npm install
npx react-native run-android

# Model integration
# Place ONNX model in assets/ and configure inference pipeline
```

## Results / Metrics

- **Validation Accuracy**: >99% on held-out test set
- **Model Size**: Optimized for mobile deployment (<50MB)
- **Inference Time**: Real-time performance on mobile devices
- **Hackathon Recognition**: Highly Commended / Top Finalist at AI for Sustainability Hackathon

## Limitations

- Dataset scope limited to four common plastic types (HDPE, PET, PP, PS)
- Performance may degrade with poor lighting or heavily occluded objects
- Requires periodic retraining as new plastic types are introduced
- Mobile inference performance varies by device hardware

## Roadmap

- Expand classification to additional plastic types and composite materials
- Implement batch processing for industrial sorting applications
- Add confidence calibration and uncertainty quantification
- Develop web dashboard for model monitoring and retraining workflows
- Integrate with recycling facility databases for end-to-end tracking

## Links

- **GitHub**: https://github.com/will702/PlastiDesk
- **Documentation**: See `docs/` for LaTeX reports and deployment handbook
