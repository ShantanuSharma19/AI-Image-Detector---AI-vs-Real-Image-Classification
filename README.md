# AI-Image-Detector: AI vs Real Image Classification

A CNN-based image classification system built with Python and EfficientNet to distinguish AI-generated images from real photos. This project includes end-to-end preprocessing and evaluation workflows, achieving **92.3% benchmark accuracy**.

## 🎯 Project Overview

This project addresses the growing challenge of identifying AI-generated images in an era of sophisticated image synthesis. Using deep learning techniques, specifically the EfficientNet architecture, the system can accurately classify images as either AI-generated or real with high precision.

## ✨ Key Features

- **High Accuracy**: Achieves 92.3% classification accuracy
- **EfficientNet Architecture**: Utilizes the efficient and powerful EfficientNet model
- **End-to-End Pipeline**: Complete preprocessing and evaluation workflows
- **Easy to Use**: Simple interfaces for training, evaluation, and inference
- **Real-time Classification**: Fast inference for practical applications

## 📋 Table of Contents

- [Installation](#installation)
- [Dataset](#dataset)
- [Usage](#usage)
- [Model Architecture](#model-architecture)
- [Results](#results)
- [Contributing](#contributing)

## 🔧 Installation

### Prerequisites

- Python 3.8 or higher
- pip or conda package manager
- GPU support recommended (CUDA-compatible GPU)

### Setup

1. Clone the repository:
```bash
git clone https://github.com/ShantanuSharma19/AI-Image-Detector---AI-vs-Real-Image-Classification.git
cd AI-Image-Detector---AI-vs-Real-Image-Classification
```

2. Create a virtual environment (optional but recommended):
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install required dependencies:
```bash
pip install -r requirements.txt
```

## 📊 Dataset

The model is trained on a dataset of AI-generated and real images. The dataset should be organized as follows:

```
data/
├── train/
│   ├── ai_generated/
│   └── real/
├── val/
│   ├── ai_generated/
│   └── real/
└── test/
    ├── ai_generated/
    └── real/
```

### Dataset Specifications

- **Training samples**: [Specify your dataset size]
- **Validation samples**: [Specify your dataset size]
- **Test samples**: [Specify your dataset size]
- **Image format**: JPEG, PNG
- **Image resolution**: Preprocessed to standard dimensions

## 🚀 Usage

### Training the Model

```python
from train import train_model

# Train the model
train_model(
    data_path='data/',
    epochs=50,
    batch_size=32,
    learning_rate=0.001,
    save_path='models/efficientnet_model.h5'
)
```

### Evaluating the Model

```python
from evaluate import evaluate_model

# Evaluate on test set
metrics = evaluate_model(
    model_path='models/efficientnet_model.h5',
    test_data_path='data/test/'
)

print(f"Accuracy: {metrics['accuracy']}")
print(f"Precision: {metrics['precision']}")
print(f"Recall: {metrics['recall']}")
print(f"F1-Score: {metrics['f1_score']}")
```

### Making Predictions

```python
from predict import classify_image

# Classify a single image
result = classify_image(
    image_path='path/to/image.jpg',
    model_path='models/efficientnet_model.h5'
)

print(f"Classification: {result['label']}")
print(f"Confidence: {result['confidence']:.2%}")
```

## 🧠 Model Architecture

The project uses **EfficientNet** as the backbone architecture due to its:

- Superior accuracy-efficiency trade-off
- Scalability across different model sizes
- Effective feature extraction for image classification
- Pre-trained weights on ImageNet for transfer learning

### Key Components

1. **Data Preprocessing**
   - Image normalization
   - Augmentation techniques
   - Resizing to standard dimensions

2. **Model Architecture**
   - EfficientNet backbone
   - Custom classification head
   - Dropout for regularization

3. **Training Pipeline**
   - Cross-entropy loss
   - Adam optimizer
   - Learning rate scheduling
   - Early stopping

## 📈 Results

### Performance Metrics

| Metric | Value |
|--------|-------|
| Accuracy | 92.3% |
| Precision | [Your precision] |
| Recall | [Your recall] |
| F1-Score | [Your F1-score] |

### Confusion Matrix

[Include visualization or description of your confusion matrix]

### Model Performance Graphs

- Loss curves (training vs validation)
- Accuracy curves (training vs validation)
- ROC curve
- Precision-Recall curve

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss proposed changes.

### Steps to Contribute

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 👨‍💻 Author

**Shantanu Sharma**
- GitHub: [@ShantanuSharma19](https://github.com/ShantanuSharma19)

## 🙏 Acknowledgments

- EfficientNet architecture by [Google Brain](https://github.com/google/automl)
- The open-source community for tools and libraries
- Dataset contributors

## 📞 Support

If you have any questions or issues, please open an issue on the GitHub repository.

---

**Last Updated**: 2024
