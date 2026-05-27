# Dimensionality-Reduction-in-scRNA-seq-Data

## Overview
This project presents a comparative evaluation of different clustering and dimensionality reduction techniques for Single-Cell RNA Sequencing (scRNA-seq) data analysis. The study focuses on understanding how modern deep learning–based representation learning methods perform against traditional clustering pipelines in handling high-dimensional, sparse, and noisy biological datasets.

The project evaluates four major approaches:
  IGCLAPS – Graph-Based Contrastive Learning
  scCRT – Transformer-Based Representation Learning
  scGCL – Graph Contrastive Learning
  UIPBC – Classical PCA-Based Clustering Pipeline

The models were tested on multiple publicly available scRNA-seq datasets from the GEO repository using clustering evaluation metrics such as ARI, NMI, and Purity.

## Objectives
- Compare classical and deep learning–based clustering approaches for scRNA-seq data.
- Analyze clustering quality across multiple biological datasets.
- Evaluate robustness, stability, and representation quality of each method.
- Identify the most effective dimensionality reduction strategy for scRNA-seq analysis.

## Technologies & Tools Used
- Python
- scRNA-seq Datasets (GEO Repository)
- Machine Learning & Deep Learning Techniques
- Graph-Based Contrastive Learning
- Transformer-Based Representation Learning
- PCA-Based Clustering Pipelines

### Evaluation Metrics
- Adjusted Rand Index (ARI)
- Normalized Mutual Information (NMI)
- Purity Score

## Dataset
The project uses 9 publicly available GEO scRNA-seq datasets with varying:
- Number of cells
- Number of genes
- Cluster complexity
This ensures a fair and generalized comparison across different biological conditions and dataset structures.

## Methodology
### 1. Data Preprocessing:
- Data normalization
- Removal of low-quality genes and cells
- Feature selection
- Standard preprocessing across all models for fair comparison

### 2. Dimensionality Reduction & Clustering:
Each framework generated low-dimensional embeddings from high-dimensional gene expression data:
- Transformer-based representations
- Graph-based embeddings
- PCA-based embeddings
Clustering was then applied using the recommended strategy for each framework.

### 3. Performance Evaluation:
The clustering quality was evaluated using:
- ARI for clustering similarity
- NMI for shared cluster information
- Purity for cluster homogeneity

## Models Compared
### 1. IGCLAPS
A graph-based contrastive learning framework that improves clustering robustness by learning relationships between biologically similar cells.

### 2. scCRT
A transformer-based model using self-attention mechanisms to capture global gene relationships and generate stable representations.

### 3. scGCL
A graph contrastive learning model focused on strong cell-cell embeddings and handling sparsity in scRNA-seq data.

### 4. UIPBC
A traditional PCA-based clustering pipeline serving as the baseline approach.

## Results
### Key Results:
- Deep learning–based approaches consistently outperformed classical clustering pipelines.
- scCRT achieved the best overall performance on most datasets.

### Best Performing Metrics (scCRT)
- ARI: ~0.73
- NMI: ~0.80
- Purity: ~0.90

### Major Insights
- Transformer-based representation learning produced the most stable and accurate clustering results.
- Graph-based methods improved robustness but remained sensitive to graph quality and sparsity.
- Classical PCA pipelines were computationally efficient but less capable of capturing complex nonlinear biological structures.

## Conclusion
This project demonstrates that advanced representation learning methods significantly improve clustering performance in scRNA-seq analysis. Transformer-based models, particularly scCRT, showed superior robustness, stability, and clustering accuracy across heterogeneous datasets.

The study highlights the importance of representation learning in bioinformatics and provides insights into selecting suitable dimensionality reduction techniques for real-world scRNA-seq applications.

## Future Scope
- Integrate the scCRT representation learning strategy into the UIPBC pipeline.
- Extend analysis using:
    Biological annotations
    Pathway analysis
    Functional interpretation techniques
- Explore more scalable and interpretable deep learning frameworks for large-scale scRNA-seq datasets.

## How to Run
### 1. Clone Repository
git clone <repository-link>
cd <repository-name>

### 2. Install Dependencies
pip install -r requirements.txt

### 3. Download Datasets
Download the required GEO datasets and place them inside the datasets/ folder.

### 4. Run Preprocessing
python preprocessing/preprocess.py

### 5. Train & Evaluate Models
python models/train.py

### 6. Generate Results
python evaluation/evaluate.py
