# CIFAR-10-Object-Recognition-using-ResNet50

# CIFAR-10 Object Recognition using ResNet50

## 📌 Project Overview
This project implements object recognition on the **CIFAR-10** dataset using a **ResNet50** deep learning model. The model is trained to classify images into 10 different categories, achieving high accuracy with transfer learning and data augmentation techniques.

## 📂 Dataset
The CIFAR-10 dataset consists of **60,000** color images of size **32x32** pixels, categorized into **10 classes**:
- Airplane
- Automobile
- Bird
- Cat
- Deer
- Dog
- Frog
- Horse
- Ship
- Truck

Each class has **6,000 images**, and the dataset is divided into **50,000 training** and **10,000 testing** images.

## 🚀 Features
- **Pretrained ResNet50 model** for feature extraction and fine-tuning
- **Data augmentation** to enhance model generalization
- **Efficient training pipeline** with early stopping and learning rate scheduling
- **Evaluation metrics** including accuracy, loss curves, and confusion matrix

## 🛠️ Installation
To set up the environment, install the required dependencies:

```bash
pip install tensorflow keras numpy matplotlib seaborn kaggle
```

## 📜 Implementation Steps
1. **Import Dependencies**: Load necessary packages for deep learning and visualization.
2. **Dataset Handling**:
   - Download CIFAR-10 dataset using Kaggle API:
     ```bash
     !mkdir -p ~/.kaggle
     !cp kaggle.json ~/.kaggle/
     !chmod 600 ~/.kaggle/kaggle.json
     !kaggle competitions download -c cifar-10
     ```
   - Extract and preprocess images.
3. **Load and Preprocess CIFAR-10**: Normalize images and apply data augmentation.
4. **Train-Test Split**: Divide dataset into training and testing sets.
5. **Build ResNet50 Model**:
   - Use a pretrained ResNet50 model (without top layers) and fine-tune it.
   - Add custom dense layers for classification.
6. **Compile and Train Model**: Set loss function, optimizer, and callbacks.
7. **Evaluate Performance**: Measure accuracy, visualize loss curves, and plot confusion matrix.
8. **Save and Deploy Model**: Save the trained model for future inference.

## 🖼️ Model Architecture
- **Input Layer**: 32x32 RGB images
- **Feature Extractor**: Pretrained ResNet50 layers (with ImageNet weights)
- **Fully Connected Layer**: Custom dense layers for CIFAR-10 classification
- **Output Layer**: 10 softmax neurons (one for each class)

## 📊 Results
| Metric      | Value |
|------------|--------|
| Accuracy   | 85-90% |
| Loss       | ~0.4   |

> *Results may vary depending on hyperparameters and training setup.*

## 🔥 Usage
Run the Jupyter Notebook:
```bash
jupyter notebook "CIFAR-10 Object Recognition using ResNet50.ipynb"
```

To use the trained model for predictions:
```python
import tensorflow as tf
import numpy as np
from tensorflow.keras.preprocessing import image

model = tf.keras.models.load_model("cifar10_resnet50.h5")
img = image.load_img("sample_image.jpg", target_size=(32, 32))
img_array = image.img_to_array(img) / 255.0
img_array = np.expand_dims(img_array, axis=0)
predictions = model.predict(img_array)
print("Predicted Class:", np.argmax(predictions))
```

## 📌 Future Improvements
- Train with a **deeper ResNet** model for better accuracy
- Apply **semi-supervised learning** to leverage unlabeled data
- Implement **real-time inference** for object detection applications

## 📜 License
This project is licensed under the **MIT License**.

## 🤝 Contributing
Feel free to submit issues and pull requests to enhance the project!

## 📬 Contact
For queries or collaborations, reach out via [GitHub Issues](https://github.com/your-repo/issues).

