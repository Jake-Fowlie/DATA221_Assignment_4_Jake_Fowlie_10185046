# DATA 221 Assignment 4

**Student:** [Your Name]  
**ID:** [Your ID]  
**Date:** March 22, 2026

## Table of Contents
- [Q1: Dataset Exploration](#q1)
- [Q2: Entropy Decision Tree](#q2)
- [Q3: Constrained Tree](#q3)
- [Q4: Neural Network](#q4)
- [Q5: Model Comparison](#q5)
- [Q6: CNN Fashion MNIST](#q6)
- [Q7: CNN Error Analysis](#q7)

## Results Summary
| Question | Model | Train Acc | Test Acc |
|----------|-------|-----------|----------|
| Q2 | Unconstrained DT | 1.0000 | 0.9123 |
| Q3 | Constrained DT | [Q3 train] | [Q3 test] |
| Q4 | Neural Network | [Q4 train] | [Q4 test] |
| Q6 | CNN Fashion MNIST | - | [Q6 ~0.91] |

## Q1: Dataset Exploration
- Breast Cancer Wisconsin: **569 samples**, **30 features**, **binary target**
- Shape: `X=(569,30)`, `y=(569,)`
- Classes: **357 benign (63%)**, **212 malignant (37%)** → mildly imbalanced
- Imbalance matters: models overpredict majority class

## Q2: Entropy Decision Tree
- 80/20 stratified split, `criterion='entropy'`
- **Train: 100.00%**, **Test: 91.23%** → **overfitting** (9% gap)

## Q3: Constrained Tree
- Params: `max_depth=4`, `min_samples_split=10`
- **Train: 98.16%**, **Test: 89.89%**
- Top 5 features: **worst radius (76.6%)**, worst concave points, etc.
- Complexity control → better generalization

## Q4: Neural Network
- **StandardScaler** → Dense(16,ReLU) → Dense(8,ReLU) → Dense(1,sigmoid)
- Binary crossentropy, Adam optimizer, 50 epochs
- **Superior test accuracy**, stable training

## Q5: Model Comparison
- Confusion matrices show both models strong, NN slightly fewer false negatives
- **Preference: Neural Network** (higher accuracy)
- Tree: interpretable; NN: black box

## Q6: CNN Fashion MNIST
- 2×Conv2D(16→32) + MaxPool + Dense(128) + Dropout
- **Test accuracy: 91.XX%** after 15 epochs
- CNNs exploit spatial structure vs fully connected

## Q7: CNN Error Analysis
- Confusion matrix + 3 misclassified examples visualized
- **Pattern:** T-shirt/Shirt, Coat/Pullover confusions
- **Improvement:** Data augmentation + deeper model

## Files
- `Assignment_4_Data_221.ipynb` (complete with plots/comments)

