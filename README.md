# Industrial Defect Detection

## Overview
This project implements a deep learning model to automatically detect defects in industrial equipment through image classification. The model classifies equipment images into 'defective' and 'non-defective' categories, with additional defect type labeling for defective cases.

## Project Structure
```
industrial-defect-detection/
├── data/
│   ├── raw/                  # Original image dataset
│   └── processed/            # Preprocessed images
├── models/                   # Saved model checkpoints
├── notebooks/               
│   ├── Industrial_Image_Detection.ipynb
├── requirements.txt
└── README.md
```

## Requirements
- Python 3.8+
- PyTorch 2.0+
- torchvision
- numpy
- pandas
- scikit-learn
- matplotlib
- albumentations

Install dependencies:
```bash
pip install -r requirements.txt
```

## Dataset
The dataset consists of industrial equipment images divided into:
- Non-defective samples
- Defective samples with labeled defect types:
  - Surface cracks
  - Corrosion
  - Deformation
  - Missing components

## Model Architecture
The project uses a CNN-based architecture with:
- ResNet50 backbone (pretrained on ImageNet)
- Custom classification head
- Focal Loss for handling class imbalance

## Training
1. Prepare your dataset:
```bash
python src/data/preprocess.py --input_dir data/raw --output_dir data/processed
```

2. Train the model:
```bash
python src/models/train.py --data_dir data/processed --model_dir models
```

## Evaluation Metrics
The model's performance is evaluated using:
- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix
- ROC-AUC Curve

## Results
Example performance metrics on the test set:
```
Accuracy: 0.94
Precision: 0.92
Recall: 0.95
F1-Score: 0.93
```

## Usage
For inference on new images:
```python
from src.models.model import DefectDetector

# Load trained model
model = DefectDetector.load_from_checkpoint('models/best_model.pth')

# Predict
prediction = model.predict('path/to/image.jpg')
```

## Development Timeline
- Day 1: Data collection, preprocessing, and exploratory data analysis
- Day 2: Model development, training, and initial evaluation
- Day 3: Fine-tuning, comprehensive evaluation, and documentation

## Future Improvements
- Implement multi-label classification for simultaneous defect type detection
- Add explainability features using Grad-CAM
- Deploy model as a REST API
- Add real-time processing capabilities

## Contributing
1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License
This project is licensed under the MIT License - see the LICENSE file for details.
