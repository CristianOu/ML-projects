## Task 1: Theory - Mapping it out

The purpose of this task is for you to create your own connections and overview of methods.

List of Methods:

- Principal Component Analysis (PCA)
- Kernel PCA
- Independent Component Analysis (ICA)
- Canonical Correlation Analysis (CCA)
- [Improving Model Convergence](https://chatgpt.com/c/66e0160e-4808-8004-8182-4ff58ed4bb49)Linear Discriminant Analysis (LDA
- Multidimensional Scaling (MDS)
- Isomap
- Locally Linear Embedding (LLE)
- Spectral Embedding
- t-Distributed Stochastic Neighbor Embedding (t-SNE)
- Uniform Manifold Approximation and Projection (UMAP)

List of Properties:

- supervised (can use class labels)
- feasible for continuous and/or discrete data
- can it handle missing data?
- Does it use local information?
- Does it preserve local or global structure?
- Assumes linear relationship or can handle non-linear relationship
- the original data can be reconstructed
- robust to noise
- can handle different dimensions in input

'''Your task:'''
Select at least 6 methods, and 4 properties. Assign the properties to the methods. Mark areas where you are uncertain.
You are free to add methods and properties to the list.

## Solution:

| **Property**                 | **PCA** | **LDA** | **MDS** | **ICA** | **CCA**   | **Kernel PCA** |
| ---------------------------------- | ------------- | ------------- | ------------- | ------------- | --------------- | -------------------- |
| **Supervised**               | No            | Yes           | No            | No            | Semi-supervised | No                   |
| **Linear/Non-linear**        | Linear        | Linear        | Both          | Linear        | Linear          | Non-linear           |
| **Data Reconstruction**      | Yes           | No            | No            | Yes           | No              | Partial              |
| **Robust to Noise**          | No            | Moderate      | Sensitive     | Moderate      | Sensitive       | Moderate             |
| **Continuous/Discrete Data** | Continuous    | Continuous    | Both          | Continuous    | Continuous      | Continuous           |
| **Handle Missing Data**      | No            | No            | No            | No            | No              | No                   |

## Task 2: From Theory to Practise

b) How can PCA be used to perform regression? Explain the steps. (If necessary revisit what the term regression means.)

## Solution:

Principal Component Analysis (PCA) can be used to perform regression when dealing with high-dimensional data,
where the goal is to reduce dimensionality while retaining the most significant variance and then performing
regression on the reduced feature set.
Steps:

1. Standardize the Data

- Since PCA is sensitive to the scale of data, the first step is to standardize the dataset by ensuring that each feature has a mean of zero and a standard deviation of one.
- This is done by subtracting the mean of each feature and dividing by its standard deviation.

2. Apply PCA on the Features

- Compute the covariance matrix of the standardized data.
- Calculate the eigenvectors and eigenvalues of the covariance matrix.
- Sort the eigenvectors based on their corresponding eigenvalues in descending order.

3. Choose the Number of Principal Components

- Based on the explained variance by each principal component, decide how many components to keep. Typically, components that capture the most variance (e.g., 90% of the variance) are retained.
- This reduces the dimensionality of the problem while preserving the most important information.

4. Transform the Data to the Reduced Feature Space

- Project the original feature set onto the selected principal components. The resulting data set will have fewer features (components) but still retain most of the original data's variance.

5. Perform Regression on the Reduced Data

- Use the reduced data (principal components) as input features for regression. This could be a simple linear regression, ridge regression, or any other suitable method.

6. Make Predictions

- Once the regression model is trained, use it to make predictions. The regression is performed in the space of the principal components, so the prediction process works the same way as traditional regression.

7. Inverse Transform (Optional)

- If needed, the predicted values can be transformed back to the original feature space using the inverse transformation of PCA. This step is optional and depends on the specific requirements of the problem.

## Task 2: From Theory to Practise

c) When performing dimensionality reduction via PCA using sklearn.decomposition.PCA, how do you have to set the input parameters?

## Solution:

When performing dimensionality reduction via PCA using `sklearn.decomposition.PCA`, you have to set the following input parameters:

- `n_components`: The number of components to keep. This parameter specifies the desired dimensionality of the output data. It can be an integer specifying the exact number of components to keep or a float between 0 and 1 indicating the percentage of variance to preserve.
- `svd_solver`: The solver to use for the singular value decomposition (SVD). The possible values are 'auto', 'full', 'arpack', 'randomized'. The default value is 'auto', which automatically chooses the most efficient solver based on the input data. The algorithm efficiently decomposes the data into its principal components and is mathematically robust for the task.
- `whiten`: Whether to whiten the data or not. Whitening the data means that the transformed data will have a unit variance and zero mean. This can be useful if the features have different variances or if the data is not normally distributed.
- `random_state`: Used when the ‘arpack’ or ‘randomized’ solvers are used. The random seed used by the random number generator. This parameter is used to control the randomness in the algorithm, ensuring reproducibility of the results.
- `copy`: Whether to copy the input data or not. If set to False, the input data will be overwritten. This can be useful for saving memory when working with large datasets.
- `iterated_power`: The number of iterations for the power method computation. This parameter is used to compute the SVD of the data matrix. Increasing the number of iterations can improve the accuracy of the results but may also increase the computation time.
- `tol`: The tolerance for the singular value decomposition. This parameter specifies the tolerance for the algorithm to converge. A lower tolerance value can lead to more accurate results but may also increase the computation time.
- `n_oversamples`: This parameter is only relevant when svd_solver="randomized". The number of random vectors to generate for the randomized SVD solver. This parameter is used to improve the accuracy of the randomized SVD algorithm by generating additional random vectors. Increasing this parameter can improve the quality of the approximation but may also increase the computation time.
- `power_iteration_normalizer`: This parameter is only relevant when svd_solver="randomized". The normalization method used in the power iteration method. The possible values are 'QR' or 'LU'. This parameter affects the stability and convergence of the algorithm.

Info source: [https://scikit-learn.org/stable/modules/generated/sklearn.decomposition.PCA.html](https://scikit-learn.org/stable/modules/generated/sklearn.decomposition.PCA.html)
