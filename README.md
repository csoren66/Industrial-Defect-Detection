# Industrial Defect Detection

## Overview
This project implements a deep learning model to automatically detect defects in industrial equipment through image classification. The model classifies equipment images into 'defective' and 'non-defective' categories.

## Project Structure
```
industrial-defect-detection/
├── dataset/
│   ├── casting_data/casting_data/train/                  # Training image dataset
│   └── /casting_data/casting_data/test/                  # Testing image dataset
├── models/                   # Saved model checkpoints
├── notebooks/               
│   ├── Industrial_Image_Detection.ipynb
├── requirements.txt
└── README.md
```

## Requirements
- opencv-python
- pandas
- numpy
- seaborn
- matplotlib
- holoviews
- tensorflow
- scikit-learn
- shap
- json

Install dependencies:
```bash
pip install -r requirements.txt
```

## Dataset
The dataset consists of industrial equipment images divided into:
- Defective
- Non-defective


## Model Architecture
The project uses a CNN-based architecture with:
```
Model: "sequential"
_________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 conv2d (Conv2D)             (None, 150, 150, 16)      800       
                                                                 
 max_pooling2d (MaxPooling2  (None, 75, 75, 16)        0         
 D)                                                              
                                                                 
 conv2d_1 (Conv2D)           (None, 75, 75, 32)        4640      
                                                                 
 max_pooling2d_1 (MaxPoolin  (None, 37, 37, 32)        0         
 g2D)                                                            
                                                                 
 conv2d_2 (Conv2D)           (None, 37, 37, 64)        18496     
                                                                 
 max_pooling2d_2 (MaxPoolin  (None, 18, 18, 64)        0         
 g2D)                                                            
                                                                 
 flatten (Flatten)           (None, 20736)             0         
                                                                 
 dense (Dense)               (None, 224)               4645088   
                                                                 
 dropout (Dropout)           (None, 224)               0         
                                                                 
 dense_1 (Dense)             (None, 1)                 225       
                                                                 
=================================================================
Total params: 4669249 (17.81 MB)
Trainable params: 4669249 (17.81 MB)
Non-trainable params: 0 (0.00 Byte)
_________________________________________________________________
```

## Contributing
1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License
This project is licensed under the MIT License - see the LICENSE file for details.
