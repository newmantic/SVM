# SVM


Support Vector Machines (SVM) are a type of supervised learning algorithm used for classification and regression tasks. The primary goal of an SVM is to find the optimal hyperplane that separates data points of different classes with the maximum margin.


A hyperplane is a decision boundary that separates different classes in the feature space. For a dataset with n features, a hyperplane is an n-1 dimensional subspace. 
The equation of a hyperplane can be written as:
w^T * x + b = 0
Where w is the weight vector (normal to the hyperplane), x is the feature vector, and b is the bias term.

Margin:
The margin is the distance between the hyperplane and the nearest data points from each class. The SVM aims to maximize this margin.
Data points that lie on the margin boundaries are called support vectors.

Optimization Problem:
The SVM optimization problem involves finding the weight vector w and bias b that maximize the margin. This can be expressed as:
Minimize:  0.5 * ||w||^2
Subject to:  y_i * (w^T * x_i + b) >= 1  for all i
Where y_i are the labels (+1 or -1) of the data points x_i.

Dual Problem:
The optimization problem can also be formulated in its dual form. The dual problem focuses on finding the Lagrange multipliers alpha that maximize the dual objective:
Maximize:  sum(alpha_i) - 0.5 * sum(sum(alpha_i * alpha_j * y_i * y_j * (x_i^T * x_j)))
Subject to:  sum(alpha_i * y_i) = 0
            0 <= alpha_i <= C  for all i
Where C is a regularization parameter that controls the trade-off between maximizing the margin and minimizing the classification error.

Kernels:
When the data is not linearly separable in the original feature space, kernels are used to transform the data into a higher-dimensional space where it may become linearly separable.

Common kernels:
Linear Kernel: K(x_i, x_j) = x_i^T * x_j
Polynomial Kernel: K(x_i, x_j) = (x_i^T * x_j + c)^d
Radial Basis Function (RBF) Kernel: K(x_i, x_j) = exp(-gamma * ||x_i - x_j||^2)

Support Vectors:
The support vectors are the data points closest to the hyperplane, and they define the margin. Only these points are used to construct the optimal hyperplane.
The decision function for classifying a new data point x is given by:
f(x) = sign(sum(alpha_i * y_i * K(x_i, x)) + b)
Where the summation is over all support vectors.

Soft Margin SVM:
In cases where the data is not perfectly separable, SVMs can allow some misclassification by introducing a soft margin. This is controlled by the parameter C, which penalizes misclassification:
A large C results in a smaller margin but fewer misclassification errors.
A small C allows a larger margin but potentially more misclassification.

