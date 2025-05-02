# Implementing and Evaluating CNNs on MedMNIST

## 1. Accuracy and Loss Analysis
### 📈 Accuracy Curves:
  From the plotted accuracy curves:
  
  MiniVGG consistently outperforms LeNet in training, validation, and test accuracy across all 10 epochs.
  
  MiniVGG reaches >90% training accuracy by epoch 6, while LeNet struggles to cross 75%.
  
  Test accuracy for MiniVGG converges close to 84%, whereas LeNet settles around 72%.

### 📉 Loss Curves:
  MiniVGG shows a more stable and steep decline in training and validation loss.
  
  LeNet's validation and test loss fluctuate more, indicating less stable generalization.
  
  MiniVGG achieves lower loss across all sets, particularly validation loss which drops below 0.4, compared to LeNet's ~0.75.


## 2. Evaluation Metrics Interpretation
  ### 📊 Confusion Matrices:
    MiniVGG displays tighter clustering on the diagonal, indicating better class-wise prediction accuracy.
    
    LeNet shows significant misclassification especially in classes like 2, 3, 5, and 7.

  ### 📋 Classification Report Summary:
      LeNet:
      Accuracy: 72.42%
      
      Macro F1: 66.89%
      
      Worst class (F1): Class 7 — 0.44
      
      Strongest class: Class 0 — 0.91
      
      MiniVGG:
      Accuracy: 84.15%
      
      Macro F1: 77.62%
      
      Significant improvement across all classes.
      
      Best class (F1): Class 0 — 0.96, Class 1 — 0.94
      
      Class 7 remains weak — F1: 0.35, but better than LeNet.

## 3. Best-Performing Model
  ✅ MiniVGG is the best-performing model.
  
  Justification:
  
  Achieves higher accuracy (84% vs. 72%)
  
  Demonstrates better loss convergence.
  
  Higher F1 scores for almost all classes.
  
  Less overfitting and better generalization.

## 4. Accuracy Improvement in Early Epochs
  MiniVGG improved from ~55% to ~80% accuracy in the first 3 epochs, showing rapid learning.
  
  LeNet improved slowly from ~41% to ~63% in the same period.
  
  MiniVGG had a faster accuracy gain in early epochs due to its deeper and better-regularized architecture.

## 5. Model Complexity and Impact
  MiniVGG has significantly more parameters due to:
  
  More convolutional layers
  
  Larger fully connected layers
  
  Dropout layers adding regularization

  ### Effect:

  Slower training time per epoch
  
  But better feature extraction, improved generalization, and higher ceiling performance
  
  LeNet is faster and lightweight but lacks depth for hierarchical feature learning.

## 6. Overfitting Observation
  ### LeNet:
  Shows signs of overfitting after epoch 6:
  
  Train accuracy rises slowly but test accuracy plateaus or dips.
  
  Test loss doesn't decrease as cleanly and even oscillates.

  ### MiniVGG:
  
  No clear overfitting within 10 epochs.
  
  Training and validation curves stay close.
  
  Regularization (Dropout) and deeper architecture help prevent overfitting.

## ✅ Conclusion
Both models demonstrate solid learning on the PathMNIST dataset, but MiniVGG clearly outperforms LeNet in all aspects: learning speed, generalization, class-wise performance, and stability. Its architectural complexity and regularization help it handle the multi-class classification task more effectively.


