# Head Counting for Crowd Engagement Using Computer Vision

📚 Introduction

This project uses the DT1: BD25 Bradford 2025 UK City of Culture dataset to study head counting for crowd engagement through computer vision and machine learning.

Crowd counting supports public safety monitoring, urban planning, and event management. Traditional manual counting is expensive and limited, but deep learning now allows automatic feature extraction and enhanced accuracy.

This project explores three major crowd counting methods:
	•	Detection-based approaches
	•	Regression-based approaches
	•	Density estimation-based approaches

Our study focuses on comparing VGG16 and ResNet50 architectures using transfer learning for head counting tasks based on pseudo-annotations generated by MTCNN.

🔍 Research Questions
	1.	How do VGG16 and ResNet50 compare in terms of accuracy and efficiency for head counting with pseudo-annotations?
	2.	How robust are these models when evaluated across different crowd densities, occlusions, and lighting conditions?

🗂️ Dataset
	•	135 high-resolution images (9504×6336 pixels)
	•	Automatically annotated with pseudo-labels (bounding boxes) using MTCNN face detection.

You can find the dataset here on Kaggle 🔗: /kaggle/input/crowd-data/Train Data .

⚙️ Methodology
	•	Pseudo-labeling: MTCNN detects heads to create bounding box labels.
	•	Preprocessing:
	•	Image resizing and normalization (ImageNet standards)
	•	Data augmentation: brightness/contrast adjustment, rotations, random erasing
	•	Model Selection:
	•	VGG16 and ResNet50 (pre-trained on ImageNet)
	•	Last layers modified for regression (head count prediction)
	•	Optimization:
	•	VGG16: Adam optimizer
	•	ResNet50: SGD with learning rate scheduler
	•	Evaluation:
	•	Validation loss
	•	Mean Squared Error (MSE) and Mean Absolute Error (MAE) on augmented data

📊 Results

| Model    | Validation Loss | Training Time  | MSE (Augmented) | MAE (Augmented) |
|----------|-----------------|----------------|-----------------|-----------------|
| VGG16    | 45.5504          | 16 min 46 sec  | 1069.0226       | 30.8478         |
| ResNet50 | 30.9412          | 16 min 42 sec  | 188.1732        | 12.5612         |

	•	ResNet50 outperforms VGG16, achieving lower validation loss and better robustness under data augmentation.
	•	ResNet50 is better suited for complex, real-world crowd counting scenarios.


🖥️ Computational Environment
	•	Hardware: P100 GPU (Kaggle Notebook)
	•	Libraries:
	•	Python 3.x
	•	TensorFlow / PyTorch
	•	OpenCV
	•	Scikit-learn
	•	Matplotlib / Seaborn
	•	MTCNN

🚀 Future Work
	•	Extend to larger and more diverse datasets
	•	Explore domain adaptation techniques for improved cross-environment generalization
	•	Apply semi-supervised learning strategies to reduce reliance on pseudo-labels

📜 Citation

If you use this work, please cite:

Author: Esther Okonkwo
Project Title: Head Counting for Crowd Engagement Using Computer Vision
Year: 2025
