# Melanoma Detection using Transfer Learning (ISIC 2020)

A deep learning-based skin cancer classification project using transfer learning to distinguish malignant melanoma from benign skin lesions. Trained and evaluated on the ISIC 2020 Challenge Dataset, this project benchmarks the performance of multiple CNN architectures with metrics across training, validation, and test sets.

---

## Dataset

- Source: [ISIC 2020: Skin Lesion Analysis Towards Melanoma Detection](https://challenge.isic-archive.com/data/)
- Size: ~45GB dermoscopic image dataset
- Format: JPEG images with binary labels (benign vs malignant)

---

## Models Used

The following pre-trained models were fine-tuned on the dataset:

- MobileNetV2  
- EfficientNetB0  
- DenseNet121  
- ResNet50  
- VGG16

All models were trained for 100 epochs with:
- Image size: 224×224  
- Optimizer: Adam  
- Loss Function: Binary Crossentropy  
- Augmentations: Rotation, flipping, brightness, and zoom  
- Class balancing: Downsampling majority class

---

## Performance Metrics

| Model         | Train Accuracy | Val Accuracy | Test Accuracy | Train Loss | Val Loss |
|---------------|----------------|--------------|----------------|------------|----------|
| ResNet50      | 97.55%         | 80.91%       | 77.33%         | 0.0623     | 1.5407   |
| MobileNetV2   | 96.56%         | 79.93%       | 82.94%         | 0.0890     | 1.0626   |
| DenseNet121   | 91.23%         | 77.45%       | 83.15%         | 0.2101     | 0.8533   |
| VGG16         | 90.07%         | 78.70%       | 78.89%         | 0.2318     | 0.9274   |
| EfficientNetB0| 90.34%         | 77.24%       | 80.69%         | 0.2249     | 0.8320   |

Best test accuracy: **DenseNet121 – 83.15%**  
Best training accuracy: **ResNet50 – 97.55%**

---

## Project Structure

```bash

├── notebooks/
│   ├── preprocessing.ipynb     # Data loading, cleaning, augmentation
│   ├── training_*.ipynb        # Model training scripts for each architecture
│   └── evaluation.ipynb        # Test set prediction and metrics comparison 
├── requirements.txt            # Python dependencies
└── README.md                   # You're here!
```

## How to Run
### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/melanoma-detection-tl.git
cd melanoma-detection-tl
```

### 2. Download the dependencies 
```bash
pip install -r requirements.txt
```
### 3. Download the ISIC Dataset
- Updata paths in notebooks if needed.

### 4. Run Preprocessing and Training
```bash
jupyter notebook notebooks/preprocessing.ipynb
jupyter notebook notebooks/training_mobilenet.ipynb  # or any other model
```

### 5. Evaluate the models
```bash
jupyter notebook notebooks/evaluation.ipynb
```

## Visualisation
This project includes
  - Training and validation accuracy/loss plots
  - Confusion matrices on test predictions
  - ROC-AUC curves for model comparison
  - Class distribution and image augmentation previews

## Contributions
Contributions are welcome!
If you find a bug or want to propose a new feature/model, feel free to open an issue or submit a pull request.
To contribute:
- Fork the repository
- Create a new branch (git checkout -b feature-branch)
- Push to the branch (git push origin feature-branch)
- Open a pull request







