# defect-classification-in-stem-images
Unsupervised machine learning framework for defect classification and clustering in atomic-resolution images using CVAE-based image reconstruction.

# About "Clustering_CdTe_Data.ipynb" notebook
This Jupyter notebook performs unsupervised clustering on a dataset of 1119 atomic-resolution HAADF-STEM images of CdTe. The image dataset is provided in the main repository under the folder named DataSet_CdTe, located within the Image Data directory.
The notebook includes the following key steps:
Feature extraction from difference images generated using CVAE-based reconstruction
Application of a three-tier feature selection process:
Pearson correlation filtering (to remove highly correlated features)
Silhouette score thresholding (to discard non-discriminative features)
Variance thresholding (to remove low-variance features)
Dimensionality reduction using Principal Component Analysis (PCA)
Clustering using k-means, with the number of clusters optimized based on silhouette score maximization
Visualization of the clustering results using t-distributed Stochastic Neighbor Embedding (t-SNE)
# Note
GitHub may not render this notebook due to its size. Please download and open in Jupyter for full functionality.
