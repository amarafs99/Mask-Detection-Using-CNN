# Real-time Mask Detection with Webcam

This repository contains a Python script for real-time mask detection using a webcam. It combines face detection with a trained convolutional neural network (CNN) to determine if a person in the video feed is wearing a mask.

## Table of Contents

- [Introduction](#introduction)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Training the Mask Detection Model](#training-the-mask-detection-model)
  - [Data Preparation](#data-preparation)
  - [Model Definition](#model-definition)
  - [Data Splitting](#data-splitting)
  - [Model Training](#model-training)
  - [Plotting Training History](#plotting-training-history)
- [Real-time Mask Detection](#real-time-mask-detection)
  - [Loading the Pre-trained Model](#loading-the-pre-trained-model)
  - [Face Detection](#face-detection)
  - [Mask Detection](#mask-detection)
  - [Live Video Display](#live-video-display)
- [Contributions](#contributions)
- [License](#license)

## Introduction

This code demonstrates how to perform real-time mask detection using a webcam. It integrates face detection with a trained CNN model to classify whether a person is wearing a mask or not.

## Getting Started

### Prerequisites

- Python 3.x
- OpenCV
- Keras
- NumPy
- Haar Cascade Classifier for face detection
- Pre-trained mask detection model ('model-005.model')

### Installation

1. Clone this repository:
git clone https://github.com/amarafs99/Mask-Detection-Using-CNN.git


## Training the Mask Detection Model

### Data Preparation

- The script assumes that there's a 'dataset' directory containing subdirectories for each class ('with_mask' and 'without_mask').
- Images are loaded and preprocessed, including resizing to 100x100 pixels and converting to grayscale.
- Labels are assigned (0 for 'with_mask' and 1 for 'without_mask').

### Model Definition

- A CNN model is created using Keras with convolutional layers, max-pooling layers, and fully connected layers.
- The model is compiled with categorical cross-entropy loss and the Adam optimizer.

### Data Splitting

- The data is split into training and testing sets using `train_test_split`.

### Model Training

- The model is trained for a specified number of epochs (5 by default) with a ModelCheckpoint callback to save the best model during training.

### Plotting Training History

- The training and validation loss curves are plotted.

## Real-time Mask Detection

### Loading the Pre-trained Model

- The saved model ('model-005.model') is loaded using Keras's `load_model` function.

### Face Detection

- The code uses a Haar Cascade Classifier for face detection on the live video feed from the webcam.

### Mask Detection

- For each detected face, the code extracts the face region, preprocesses it, and feeds it to the loaded model for prediction.
- It draws rectangles around faces and adds labels ('MASK' or 'NO MASK') based on the model's prediction.

### Live Video Display

- The code continuously displays the live video feed with face and mask detection overlays.
- Pressing 'q' quits the application.

## Contributions

Contributions to this repository are welcome! If you find any issues or have improvements to suggest, please feel free to create a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
