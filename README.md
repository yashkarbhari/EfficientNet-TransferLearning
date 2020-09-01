# EfficientNet: Improving Accuracy and Efficiency through AutoML and Model Scaling

- EfficientNet model solves the problem of different scaling methods by applying a principal method for scaling to obtain better accuracy and efficiency.

## Compound Model Scaling: A Better Way to Scale Up CNNs

In order to understand the effect of scaling the network, they systematically studied the impact of scaling different dimensions of the model. While scaling individual dimensions improves model performance, they observed that balancing all dimensions of the network—width, depth, and image resolution—against the available resources would best improve overall performance.

The first step in the compound scaling method is to perform a grid search to find the relationship between different scaling dimensions of the baseline network under a fixed resource constraint (e.g., 2x more FLOPS).This determines the appropriate scaling coefficient for each of the dimensions mentioned above, then apply those coefficients to scale up the baseline network to the desired target model size or computational budget.

This compound scaling method consistently improves model accuracy and efficiency for scaling up existing models such as __MobileNet (+1.4% imagenet accuracy)__, and __ResNet (+0.7%)__, compared to conventional scaling methods.

![](Image/1.png)

## Architecture
The effectiveness of model scaling also relies heavily on the baseline network. The resulting architecture uses mobile inverted bottleneck convolution(MBConv).

![](Image/2.png)

### Reference

Paper: [EfficientNet: Rethinking Model Scaling for Convolutional Neural Networks](https://arxiv.org/abs/1905.11946)
