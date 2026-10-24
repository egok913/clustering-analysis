\# Data Mining and Machine Learning — Project 1: Clustering



\## Project Overview



This group project explores the behavior of several clustering algorithms on synthetic datasets with different geometric structures.



The project was completed as part of the \*\*Data Mining and Machine Learning\*\* course at the University of Southern Denmark. The assignment focused on experimenting with clustering algorithms, evaluating their results using quality measures, and discussing how algorithm choice and parameter settings affect clustering performance.



The project investigates:



\* K-Means clustering

\* Gaussian Mixture Models (EM)

\* A hybrid K-Means + EM approach

\* DBSCAN

\* Outlier detection methods



\## Objectives



The project explores how different clustering algorithms behave when applied to datasets with different structures.



The main questions addressed were:



\* Which clustering algorithm is most suitable for each dataset?

\* How sensitive are the algorithms to parameter choices?

\* How well do clustering quality measures reflect the underlying data structure?

\* How do different algorithms compare in terms of clustering quality?

\* Can clustering methods also be used to identify potential outliers?



\## Datasets



Two synthetic shape datasets were investigated:



\### Aggregation



The Aggregation dataset contains several groups with different shapes and densities. It provides a useful test case for comparing algorithms that make different assumptions about cluster structure.



\### Spiral



The Spiral dataset contains intertwined spiral-shaped clusters. Its non-convex structure makes it particularly challenging for algorithms such as K-Means and Gaussian Mixture Models.



The assignment used shape datasets from the \*\*Shape Sets\*\* collection.



\## Clustering Methods



\### K-Means



K-Means was evaluated as a simple and computationally efficient baseline.



Its main limitation for these experiments is that it tends to favor approximately round or convex clusters and requires the number of clusters to be specified in advance.



\### Gaussian Mixture Model (EM)



Gaussian Mixture Models were used to model clusters as Gaussian distributions.



Compared with K-Means, GMM can handle overlapping clusters more naturally, but it also requires the number of clusters to be specified and is computationally more expensive.



\### Hybrid K-Means + EM



A combined approach was also investigated.



K-Means was first used to obtain initial cluster centers, which were then used as starting parameters for the EM/GMM clustering procedure. The motivation was that the faster K-Means procedure could provide useful initialization for EM and potentially reduce the number of iterations required for convergence.



\### DBSCAN



DBSCAN was used because it does not require the number of clusters to be specified in advance and can identify clusters with non-convex shapes.



It was particularly effective for the Spiral dataset, where the cluster structure is not well represented by spherical or Gaussian clusters.



\## Evaluation



The main clustering quality measure used throughout the experiments was the \*\*Adjusted Rand Index (ARI)\*\*.



Silhouette scores were also examined for the Spiral dataset.



The experiments included multiple parameter settings to investigate how clustering quality changes as algorithm parameters are varied.



\## Results



\### Aggregation Dataset



The results showed clear differences between the clustering approaches.



For the Aggregation dataset, the presentation reports:



| Algorithm                            |                         ARI |

| ------------------------------------ | --------------------------: |

| K-Means                              | 0.704 average across 6 runs |

| GMM                                  | 0.857 average across 6 runs |

| DBSCAN                               |                       0.872 |

| DBSCAN with ARI-optimized parameters |                   \*\*0.992\*\* |



DBSCAN produced the strongest clustering result for this dataset after parameter optimization, with \*\*ARI = 0.9917\*\*, using:



\* `eps = 1.39`

\* `min\_samples = 7`



The resulting clusters closely matched the provided true labels.



\### Spiral Dataset



The Spiral dataset demonstrated the limitations of algorithms that favor round, convex, or Gaussian-shaped clusters.



| Algorithm |   Best ARI |

| --------- | ---------: |

| K-Means   |     0.0865 |

| GMM       |     0.0835 |

| DBSCAN    | \*\*1.0000\*\* |



DBSCAN successfully recovered the spiral structure, achieving an \*\*ARI of 1.0000\*\* with:



\* `eps = 1.20`

\* `min\_samples = 2`



In contrast, K-Means and GMM were unable to reproduce the underlying spiral structure effectively.



\## Outlier Detection



The project also explored outlier detection on the Aggregation dataset.



Several approaches were considered, including:



\* Distance-based detection

\* K-nearest-neighbor (KNN) based scoring

\* Local Outlier Factor (LOF)

\* DBSCAN-based detection

\* A consensus approach combining different outlier rankings



The presentation includes visual comparisons of the resulting outlier scores and a consensus ranking of points identified as potential outliers.



\## Key Takeaways



The experiments demonstrate that \*\*there is no universally best clustering algorithm\*\*. The suitability of an algorithm depends strongly on the structure of the data.



The most important observations were:



\* K-Means provides a simple and efficient baseline but struggles with non-convex cluster structures.

\* GMM can improve upon K-Means for some datasets but still assumes a Gaussian-based representation of the clusters.

\* DBSCAN is well suited to datasets containing clusters with complex shapes.

\* Parameter selection can have a substantial effect on clustering quality.

\* DBSCAN was particularly successful on the Spiral dataset, where it achieved a perfect ARI of 1.0000.

\* Different evaluation measures can provide different perspectives on clustering quality, so they should be interpreted together with the underlying data structure and visual results.



\## Repository Contents



\* `README.md` — Project documentation

\* Project source files and/or analysis notebooks — Clustering experiments

\* Presentation — Summary of the methodology, experiments, results, and conclusions



\## Course Context



\*\*Course:\*\* Data Mining and Machine Learning

\*\*Project:\*\* Project 1 — Clustering

\*\*Institution:\*\* University of Southern Denmark (SDU)

\*\*Term:\*\* Spring 2025



This was a collaborative group project completed as part of the course.



\## Presentation



The accompanying presentation provides visualizations of the clustering experiments, including the true labels, clustering results, ARI scores, parameter comparisons, and outlier detection results.



