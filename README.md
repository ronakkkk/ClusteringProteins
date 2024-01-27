For this project, the objective is to cluster proteins based on their activity in different patients and utilize these clusters to predict clinical features. The dataset's dimensionality is initially reduced through principal component analysis. Subsequently, a hierarchical clustering algorithm is applied to the principal components, and the resulting dendrogram is visualized to aid in determining the optimal number of clusters. The underlying assumption is that proteins with similar activity patterns within clusters form interacting systems, providing valuable biological insights.

1. Dendrogram:
   ![dendogram](https://github.com/ronakkkk/ClusteringProteins/assets/37010825/57dc4b12-b38a-4fff-a283-2f483611648f)

   From above dendrogram it appears that 8 components are appropriate. Therefore, hierarchical clustering is rerun and the proteins are assigned to 8 clusters.

2. Modelling clinical features:
   A set of generalized linear predictors (LassoLars for numerical variables, Logistic Regression for categorical variables) is then fit to the clinical data, using the protein cluster activity as the independent   variables
   ![image](https://github.com/ronakkkk/ClusteringProteins/assets/37010825/fcd4a8e6-edde-4da8-9ea6-4f0a11324f92)

3. Visualization and Analysis:

   A. Gender:
   
   ![image](https://github.com/ronakkkk/ClusteringProteins/assets/37010825/2ce7072b-7d46-403d-9227-bbf7ca106c4f)
   - Activity of cluster 0 is greater in female patents, while activity in clusters 2, 3, 6 and 7 is greater in male patients.
  
   B. ER Status:
   
   ![image](https://github.com/ronakkkk/ClusteringProteins/assets/37010825/ce2f5b69-6f79-4782-97b7-4a41a4ec6507)
   - Activity in clusters 2, 4 and 5 makes positive ER status more likely, while it is less likely in patients with activity in clusters 1 and 7.

   C. PR Status:

   ![image](https://github.com/ronakkkk/ClusteringProteins/assets/37010825/46055294-3baf-47c1-aeb8-b51abb176460)
   - The same clusters are correlated in the same way with ER status.
  
   D. HER2 Final Status:

   ![image](https://github.com/ronakkkk/ClusteringProteins/assets/37010825/59f41390-e92e-4614-b013-4fb86d563e90)
   - HER2 Final status is much more likely to be negative in patients with activity in clusters 1 and 7, and more likely to be positive in patients with activity in cluster 4.
  
   E. Tumor:

   ![image](https://github.com/ronakkkk/ClusteringProteins/assets/37010825/d1f420ed-253c-4654-ae3a-059fcc3b82e4)
   - T1 tumors are most likely in patients with activity in clusters 4 and 5, and least likely in patients with activity in clusters 0 and 1.
   - T2 tumors are most likely in patients with activity in cluster 5.
   - T3 tumors are significantly less likely in patients with activity in cluster 0.
   - T4 tumors are most likely in patients with activity on cluster 0 and least likely in patients with activity in cluster 5.
  
   F. Node:

   ![image](https://github.com/ronakkkk/ClusteringProteins/assets/37010825/c05036d2-39f4-4901-9fd3-2dd33a5eba8d)
   - N0 Node is slighlty more likely in patients with activity in cluster 0, and slightly less likely in patients with activity in clusters 6 and 7.
   - N1 Node is most likely in patients with activity in cluster 4 and least likely in patients with activity in cluster 1
   - N2 Node is most likely in patients with activity in clusters 5 and 6 and least likely patients with activity in cluster 3.
   - N3 Node is most likely in patients with activity in cluster 7 and least likely in patients with activity in cluster 0.
  
   G. Metastasis-Coded:

   ![image](https://github.com/ronakkkk/ClusteringProteins/assets/37010825/fe287d64-8a3a-4ab5-8df5-13072afec961)
   - Metastasis is least likely in patients with activity in cluster 4. This result should be treated with caution, as few patients in this sample exhibit metastasis.

   H. AJCC Stage:

   ![image](https://github.com/ronakkkk/ClusteringProteins/assets/37010825/c1f9936f-0bb1-4a62-a54a-ce87124a2b8d)

   I. Vital Status:

   ![image](https://github.com/ronakkkk/ClusteringProteins/assets/37010825/b4971331-76f8-473c-b6c5-6ecc45ca4671)
   - Patients with activity in cluster 0 are most likely to die. Patients with activity in cluster 1 are least likely to die.

   J. PAM50 mRNA:

   ![image](https://github.com/ronakkkk/ClusteringProteins/assets/37010825/3694369a-3e0e-41db-bf1e-e0d45e23caf8)
   - Luminal B PAM50 RNA is most likely in patients with activity in cluster 1, and less likely in patients with activity in clusters 2 and 4. HER2-enriched PAM50 RNA is lest likely in patients with activity in cluster 1. Basal-like PAM50 RNA is most likely in patients with activity in cluster 2.

   K. RPPA Clusters:

   ![image](https://github.com/ronakkkk/ClusteringProteins/assets/37010825/47d182b0-b179-4273-bd3f-b65b1d81339b)
   - HER2 RPPA Clusters are most likely in patients with activity in cluster 4. Lum A RPPA clusters are least likely in patients with activity in cluster 5. Lum A/B clusters are least likely in patients with activity in cluster 6.
