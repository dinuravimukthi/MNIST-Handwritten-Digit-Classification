# MNIST-Handwritten-Digit-Classification
The MNIST dataset has 70000 handwritten digits with 60000 training and 10000 testing samples. Each instance is represented as an array of 784 values in the 0-255 range that can be mapped to a 28 x 28 pixel image.
<br><br>
**Author**: Yann LeCun, Corinna Cortes, Christopher J.C. Burges  
**Source**: [MNIST Website](http://yann.lecun.com/exdb/mnist/)

This project focuses on classifying the digits using a suitable classifier.<br><br>
![sample_digits](https://github.com/user-attachments/assets/d8b2af6c-e32a-4507-a3a1-9da08ddc1c8b)

## Key Steps
* Model selection<br>
Selected the most suitable classifier based on the cross-validation scores from among several (SGD classifier, Random Forest classifier, and K-Neighbors classifier).
  > Selected the K-Neighbors classifier from among the rest (cross-validation score: 0.9676, 0.9671, 0.96755)

* Hyperparameter tuning<br>
Identified the best hyperparameters using the GridSearchCV method
  > The best parameter combination caused the model to overfit (1.0 accuracy). To regularize, the model was fitted with the 4th best parameter combination.

* Error analysis<br>
Analyzed the error distribution using a Confusion Matrix.
<br>Visualized and inspected a few digit pairs that were largely misclassified as each other.

* Data augmentation<br>
Shifted the training images up, down, left, and right by 2 pixels. The augmented images were combined with the training set and were shuffled altogether.
  > Resulted in a minor improvement in accuracy (0.015%).

## Model
* K-Neighbors classifier with parameters n_neighbors=4 and weights='uniform'.
* This hyperparameter combination is ranked at the 4th position, according to the GridSearchCV results:
  > The top three combinations all lead to 1.0 model accuracy indicating overfitting

## Results
Testing accuracy: 0.9678, Cross-validation accuracy: [0.922, 0.927, 0.943, 0.959, 0.961].
<br>
The inconsistency among the cross-validation scores points out that the model has overfitted the training data to some degree.
