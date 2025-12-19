# Learning Object Pose from UAV Motion

This repository contains an implementation of a lightweight deep learning model for regressing object pose parameters from a single RGB image. The model predicts continuous pose values directly using efficient CNN backbones, making it suitable for real-time and resource-constrained settings.

## Overview

The project focuses on end-to-end pose estimation from RGB images using compact convolutional neural networks such as SqueezeNet, MobileNet, ShuffleNet, and MnasNet as feature extractors.

Given an input image, the network regresses four pose parameters:
                                                                [x, y, z, θ]
where:
- x,y,z represent translation
- θ represents rotation (e.g., yaw)

## Model Architecture

The overall architecture follows a backbone + regression head design:
                    <img width="780" height="450" alt="network" src="https://github.com/user-attachments/assets/0c783c6e-56dc-490b-9111-8bee213c5139" />
                    
**1. Input** 
- RGB image of size 360 × 640
                    <img width="780" height="450" alt="img4" src="https://github.com/user-attachments/assets/0d594aa8-93c4-4860-b16b-98c921a29331" />


**2. Backbone Network consists of one of**
- SqueezeNet
- MobileNet
- ShuffleNet
- MnasNet

Used for efficient feature extraction

**3. Regression Head**
- Fully connected (linear) layer
- Input: 1000-dimensional feature vector
- Output: 4 continuous pose values [x,y,z,θ]

The design prioritizes computational efficiency while maintaining reasonable prediction accuracy.

## Repository

<img width="450" height="200" alt="image" src="https://github.com/user-attachments/assets/dd7ca045-1127-4e2e-834d-503ccede0adb" />


## Customization

You can easily:
- Swap backbone networks
- Modify the regression head
- Extend output dimensions (e.g., full 6-DoF pose)
- Integrate multi-view inputs

🧪 **Experiments**

This project is designed to facilitate:
- Backbone comparison for pose regression
- Trade-off analysis between accuracy and inference speed
- Deployment on edge devices

  See training plots and results below: 
                  <img width="780" height="450" alt="image" src="https://github.com/user-attachments/assets/5e2a6a51-5df0-434e-bef6-e0db92fd028d" />
                  <img width="450" height="200" alt="table1" src="https://github.com/user-attachments/assets/ecb0f380-8e47-43b3-8aed-98397aad5157" />

  *Note: repository contains matlab files for generating the dataset.*
  
