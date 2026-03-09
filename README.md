Image Classification with Neural Networks and Deep Learning
Description
This project implements and compares different neural network architectures to solve a multiclass image classification problem using Keras and TensorFlow.
The following models were developed:

Two fully connected (dense) neural networks
One convolutional neural network (CNN) inspired by AlexNet
Two models using Transfer Learning
Comparative analysis through training curves and confusion matrices

All models were trained with varying numbers of epochs, applying techniques such as regularization, dropout, data augmentation, and early stopping.

Dataset
The CIFAR-10 dataset was used, containing 60,000 color images of size 32×32 distributed across 10 classes (airplane, automobile, bird, cat, deer, dog, frog, horse, ship, and truck).
This dataset was chosen because it represents an appropriate challenge for convolutional architectures and transfer learning models, while keeping computational cost reasonable for execution on Google Colab.

Models
1. Fully Connected (Dense) Networks
Two architectures were implemented:

A simple network with a single hidden layer of 1,024 neurons, L1/L2 regularization, and a softmax output layer.
A deeper network with six hidden layers, a decreasing architecture, and dropout on intermediate layers.

Both models achieved a validation accuracy of approximately 50%.
Conclusion: Dense networks are not well-suited for complex image classification. Applying Flatten discards the spatial structure of the image, causing the model to learn pixel combinations rather than structured visual patterns.
2. Convolutional Neural Network (CNN)
An architecture inspired by AlexNet was implemented, adapted to the 32×32 input size. Kernel sizes were reduced from the original and the final classifier was adjusted with regularization and dropout.
This model achieved approximately 77% accuracy on both training and validation sets.
Conclusion: The CNN significantly improves performance by preserving spatial structure and extracting local features through convolutions. Generalization was considerably better than with dense networks.
3. Transfer Learning
EfficientNetV2B0 pre-trained on ImageNet was used. Images were resized to 128×128 to match the model's expected input.
Two strategies were evaluated:

Strategy 1 — Frozen base: Only the added classifier was trained on top of the frozen base model. Result: approximately 88% validation accuracy.
Strategy 2 — Fine-tuning: The last 100 layers were unfrozen and the learning rate was reduced. Result: approximately 93% validation accuracy.

Conclusion: Transfer Learning was the most effective strategy, achieving the best performance with less training from scratch and better generalization capacity.

Results Summary
ModelValidation AccuracyDense Network (simple)~50%Dense Network (deep)~50%CNN (AlexNet-inspired)~77%Transfer Learning (frozen)~88%Transfer Learning (fine-tuning)~93%

Key Takeaways

Choosing the right architecture is fundamental in computer vision problems.
Preserving the spatial structure of images is key to good performance.
Pre-trained models can outperform complex networks trained from scratch.
The quality and scale of the original training dataset directly influences generalization capacity.
Transfer Learning proved to be the most efficient and best-performing technique for this problem.


Authors

Santiago Santos
Mateo Wagner

Course: Artificial Intelligence — 2025
