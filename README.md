# Clustering Atomic-Resolution STEM Images using CVAE-Based Anomaly Detection
This repository contains all the files necessary to reproduce the unsupervised clustering of atomic-resolution (S)TEM images based on defect types, using a CVAE-based anomaly detection and feature extraction pipeline, followed by a three-tier feature selection and k-means clustering workflow.

# 🔹 1. Clustering CdTe Dataset
# STEP 1: Training the CVAE Model for CdTe
To train the CVAE model and generate predicted images:

Download:

CdTe_CVAE_Model_Training.py

CdTe_Training_Image.tif (the training image)

Update the following paths inside the Python script:

Path to the working directory

Path to the training image (CdTe_Training_Image.tif)

Run the script.
The trained CVAE model will be saved in your working directory. This model will later be used to reconstruct bulk-like predicted images during the clustering process.

# STEP 2: Clustering the STEM Dataset
Download:

The folder DataSet_CdTe from the Image Data directory (contains 1119 .tif images)

The Jupyter notebook Clustering_CdTe_Data.ipynb

Update the paths in the notebook:

Path to the input image

Path to the CVAE model saved in Step 1

Path to the image folder DataSet_CdTe

The notebook includes the following stages:
Feature Extraction
Generate difference and filtered difference images using the CVAE model, and extract 47 pixel-intensity-based, shape-based, and frequency-based features.

Three-Tier Feature Selection

Pearson Correlation Filtering: Remove highly correlated features (threshold > 0.95)

Silhouette Score Filtering: Discard features with negative or low discriminative scores

Variance Thresholding: Remove features with variance < 0.1

Dimensionality Reduction
Apply Principal Component Analysis (PCA) to the shortlisted features.

Clustering
Perform k-means clustering, optimizing the number of clusters using silhouette score maximization.

Visualization
Use t-distributed Stochastic Neighbor Embedding (t-SNE) for 2D visualization of clustering results.

The final feature dataset can also be exported as a .csv file for future use.

# 🔹 2. Clustering SrTiO₃ (STO) Dataset
Repeat the same process as above, substituting CdTe with STO.

STEP 1: CVAE Model Training for STO
Download:

STO_CVAE_Model_Training.py

STO_Training_Image.jpg

Update paths inside the script as needed and run it to generate the trained CVAE model.

STEP 2: Clustering the STO Dataset
Download:

The folder DataSet_STO (contains 764 .tif images)

The notebook Clustering_STO_Data.ipynb

Update paths to:

The STO input image

The trained STO CVAE model

The dataset folder DataSet_STO

Follow the same pipeline for feature extraction, filtering, PCA, clustering, and visualization.

# Requirements
Ensure all required Python libraries (e.g., tensorflow, numpy, scikit-learn, matplotlib, seaborn) are installed.

This workflow has been tested with Python 3.12.3, TensorFlow 2.18.0, scikit-learn 1.5.1, and Jupyter Notebook 6.5.7.
