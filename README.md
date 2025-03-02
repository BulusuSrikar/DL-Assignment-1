# DL-Assignment-1

**MNIST Feedforward Neural Network Report**

### **1. Dataset Overview**
- Dataset: MNIST (handwritten digits, 28x28 grayscale images)
- Training Set: 54,000 images (after 10% validation split)
- Validation Set: 6,000 images
- Test Set: 10,000 images

### **2. Model Design & Hyperparameters**
- Architecture: Fully connected feedforward neural network
- Hidden Layers: {3, 4, 5 layers}
- Neurons per layer: {32, 64, 128}
- Activation Functions: {ReLU, Sigmoid}
- Optimizers: {SGD, Momentum, Nesterov, RMSprop, Adam}
- Learning Rate: {1e-3, 1e-4}
- Batch Sizes: {16, 32, 64}
- Weight Initialization: {Random, Xavier}
- Loss Function: Cross Entropy Loss

### **3. Experimentation & Results**
#### **3.1 Training & Validation Accuracy**
| Hidden Layers | Activation | Optimizer | Val Accuracy (%) |
|--------------|------------|-----------|----------------|
| [128, 64]    | ReLU       | SGD       | 91.5          |
| [128, 64]    | Sigmoid    | SGD       | 89.1          |
| [256, 128, 64] | ReLU     | Adam      | 97.2          |
| [512, 256, 128, 64] | ReLU | Adam     | 98.1          |
| [512, 256, 128, 64] | Sigmoid | RMSprop | 95.4        |

#### **3.2 Test Accuracy & Confusion Matrix**
- Best Model: **[512, 256, 128, 64], ReLU, Adam**
- Test Accuracy: **98.0%**

### **4. Loss Function Comparison**
| Loss Function     | Validation Accuracy |
|------------------|--------------------|
| Cross Entropy    | 98.1%              |
| Mean Squared Error | 92.7%             |
- Cross Entropy performed significantly better, as MSE is not ideal for classification problems.

### **5. Recommendations for MNIST**
Based on our experiments, the best hyperparameters for MNIST are:
1. **Model Architecture:** 4 hidden layers (**512, 256, 128, 64**) with **ReLU activation**
2. **Optimizer:** Adam with **learning rate = 0.001**
3. **Loss Function:** Cross Entropy (better suited for classification)

### **6. Conclusion**
- **More layers & neurons improved performance** but increased training time.
- **ReLU performed better than Sigmoid** due to better gradient flow.
- **Adam optimizer achieved the best accuracy** due to adaptive learning rates.
- **Cross Entropy outperformed MSE**, confirming it's the best loss function for classification.

These results suggest that using **ReLU activation, Adam optimizer, and Cross Entropy Loss** with **a deep network** leads to **high accuracy** on MNIST. Further improvements could be achieved by fine-tuning learning rates or using dropout for regularization.

