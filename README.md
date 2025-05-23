# Neural Networks Fundamentals

This project is part of the (cannot explicitly name it due to plagiarism prevention) course at TU Eindhoven. It focuses on the fundamentals of neural networks, with emphasis on implementing them "from scratch", without using any widely available machine learning libraries. The goal was to classify hand written digits using different model structures as well as experiment with different training types and loss functions.

## Dataset
The project is based on the [MNIST dataset](https://en.wikipedia.org/wiki/MNIST_database), which consists of 28x28 grayscale images of handwritten digits. The dataset is widely used for training and testing in the field of machine learning.

![image](https://github.com/user-attachments/assets/3f039fd6-9077-4cf3-93d0-e028f86c5b39)

## Implementation
Implemented solution focuses on comparing different learning algorithms.
![image](https://github.com/user-attachments/assets/0c40c5d5-d71f-48f9-b2c4-adb2b2627e51)

### Batch Gradient Descent (BGD)
**Model Structure:** <br>
Input layer: 784 neurons (flattened 28×28 image)<br>
Hidden layer: 64 neurons, activation: sigmoid<br>
Output layer: 10 neurons (digit classes 0–9), output activation: softmax<br>

**Hyperparameters:** epochs: 2000, alpha: 0.2, activation: sigmoid

**Results:** training time: 3432s, test accuracy: 0.925, test loss: 0.300
![image](https://github.com/user-attachments/assets/f85ab46c-eb12-47c1-b83b-a01107259282)

### Mini batch gradient descent (MBGD)
**Model Structure:** <br>
Input layer: 784 neurons (flattened 28×28 image) <br>
Hidden layer: 64 neurons, activation: sigmoid <br>
Output layer: 10 neurons (digit classes 0–9), output activation: softmax <br>

**Hyperparameters:** epochs: 200, alpha: 0.1, activation: sigmoid, batch size: 64

**Results:** training time: 620s, test accuracy: 0.933, test loss: 0.237
![image](https://github.com/user-attachments/assets/95f61edb-8e00-45c5-b5de-016f5a845888)

### Pytorch Convolutional Neural Network (CNN)
**Model Structure:** 
Input: 1×28×28 grayscale image <br>
Conv Layer 1: 32 filters, 3×3 kernel, padding=1 → ReLU → MaxPool (2×2) <br>
Conv Layer 2: 64 filters, 3×3 kernel, padding=1 → ReLU → MaxPool (2×2), Flatten: Output reshaped to 3136 features (64×7×7) <br>
Fully Connected Layer 1: 3136 → 128 → ReLU <br>
Fully Connected Layer 2: 128 → Output layer: 10 neurons (digit classes 0–9), output activation: logsoftmax

**Hyperparameters:** epochs: 10, learning rate: 0.001, batch size: 256, optimizer: Adam, activation: ReLU + LogSoftmax

**Results:** training time: 233s, test accuracy: 0.995, test loss: 0.037
![image](https://github.com/user-attachments/assets/ed9e9866-016f-4d04-9604-4ee29effd7d0)



## Running the code
### Environment Setup
It is recommended to use the course-provided "experiments_JF" environment to run the code.

### Dataset Download
The Datasets folder contains a zipped file of the MNIST dataset. This dataset includes all samples without any division into training, testing, or validation sets. To run the code, please unzip the file manually.

## Remarks
- No model saving or loading functionality has been implemented in this project. As a result, training is required for each program execution.

