# Defense Mechanisms Against Adversarial Attacks in Computer Vision

This project focuses on the implementation of a deep convolutional neural network (CNN) using the ResNet18 architecture to classify images from the CIFAR-10 dataset. Additionally, we explored adversarial attacks on the trained model and implemented defense mechanisms to counteract these attacks.

## Table of Contents

- [Dataset](#dataset)
- [Model](#model)
- [Adversarial Attacks & Defense](#adversarial-attacks--defense)
- [Conclusion](#conclusion)

## Dataset

- **CIFAR-10:** 60,000 RGB images (32x32), with 10 classes such as frogs, horses, ships, trucks etc.
  - 50,000 training images
  - 10,000 testing images

<p align="center">
  <img src="https://github.com/arushi2509/Defense-Mechanisms-Against-Adversarial-Attacks-in-Computer-Vision-/assets/69112495/f3d3b896-6780-4ae3-83dd-07a94832f83c" alt="cifar10">
</p>



## Model

- **Architecture:** ResNet18
- **Accuracy:** 96% on the training dataset and 80% on the test dataset.

## Adversarial Attacks & Defense

Various attacks were implemented on the trained model, and their impact on model performance was observed:

- **Noise Attacks** (with varying standard deviations): 
  - Stddev. 0.01 - Accuracy Drop: 0%
  - Stddev. 0.09 - Accuracy Drop: 8%
  - Stddev. 0.25 - Accuracy Drop: 32%
  - Stddev. 0.50 - Accuracy Drop: 49%

- **Other Attacks:**
  - FGSM (Fast Gradient Sign Attack)
  - PGD (Projected Gradient Descent)
  - C-W (Carlini-Wagner)

Results with different epsilon values:

| Epsilon | FGSM | PGD | C-W  |
| ------- | ---- | --- | ---- |
| 0.002   | 54.36% | 54.75% | 58.5% |
| 0.02    | 27.55% | 24.31% | 57.5% |
| 0.2     | 6.67%  | 0.6%   | 53.5% |

### Defense

A defense mechanism was implemented against the Additive Gaussian Noise Attack:

- **Defense Strategy:** Adversarial training with gaussian noise.
  - Accuracy on adversarial test set increased from 72% to 77%.


## Conclusion

The project showcases the performance of ResNet18 on the CIFAR-10 dataset and delves deep into understanding the effects of adversarial attacks. We explored the trade-off between the visual quality of the adversarial image and its impact on model performance. Furthermore, adversarial training proved to be an effective defense mechanism.


