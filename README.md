# Clustering News Articles: A Comparative Analysis
This project explores the effectiveness of various text embedding techniques and unsupervised learning algorithms in categorizing news documents. I compare performance across: the BBC News dataset and the 20NewsGroups dataset.

🚀 Project Overview
The core objective is to evaluate how different combinations of feature extraction and dimensionality reduction impact the ability of clustering algorithms to recover "ground truth" categories.

Key Features
Embeddings: TF-IDF, Word2Vec and FastText.

Dimensionality Reduction: Principal Component Analysis (PCA) used for noise reduction and fine-tuning.

Algorithms: K-Means, Agglomerative Clustering, and HDBSCAN.

Visualization: Cluster projection using t-SNE and optimal cluster discovery via the Elbow Method.

📊 Evaluation Metrics
The primary metrics:

NMI (Normalized Mutual Information): Measures the alignment between clusters and ground truth labels (0 to 1).

ARI (Adjusted Rand Index): Corrects for chance, measuring the similarity between two assignments.

AMI (Adjusted Mutual Info Score): Adjusts NMI for the effect of chance.

Silhouette Score: Measures internal cluster consistency and separation (independent of labels).

📈 Key Findings
1. The Power of TF-IDF
Despite being a "bag-of-words" approach, TF-IDF consistently outperformed neural embeddings (Word2Vec/FastText) in NMI and ARI. This suggests that for news categorization, the presence of specific keywords is a stronger signal than general semantic context.

2. PCA 
Fine-tuning revealed that 10-50 components is the optimal range for text clustering.

BBC News: Peaked at 10 components, proving that aggressive "denoising" helps K-Means identify major topics.

20NewsGroups: Required 100 components to maintain enough information to distinguish between 20 complex categories.

3. Algorithm Robustness
K-Means proved to be the most stable and accurate algorithm for both datasets.

HDBSCAN struggled with high-dimensional sparsity (often returning 0.0 NMI), but for the data it did cluster, it achieved the highest Silhouette Scores, indicating extremely dense clusters.
