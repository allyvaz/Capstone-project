<div align="center">
  <a href="https://github.com/allyvaz/Capstone-project">
    <img src="https://microbenotes.com/wp-content/uploads/2023/05/Alleles.jpg" alt="Logo" width="80" height="80">
  </a>

  <h1 align="center">PathFinder: Unraveling <i>TP53</i> Variant Pathogenicity for Clinical Insights</h1>
</div>

## Project Overview

### Areas of Interest
1. Variants of <i>TP53</i> causing Cancer.
2. Variant allele frequency of <i>TP53</i>.
3. Longitudinal study of <i>TP53</i> variants.
4. Exploration of <i>TP53</i> variant interactions with other genes or pathways implicated in Cancer development.

### Problem Statement
In cancer research, accurately identifying mutations (variants) from next-generation sequencing of tumor samples poses a significant challenge. Variants exhibit diverse characteristics within the dataset, and both biological and technical variability complicate the process for variant callers. Metrics such as sequencing depth around the variant, the count of reads supporting the reference or mutated allele, the quality associated with these reads, and the confidence level of the tools in making specific calls, are crucial for assessing variants. This project will specifically explore the utility of one such metric: Variant Allele Frequency (VAF), in addressing these challenges.

### Proposed Data Science Strategy
1. Prioritize <i>TP53</i> variants based on their predicted functional impact, frequency in the dataset, and relevance to pathogenesis.
2. Utilize machine learning algorithms, such as random forests, to rank <i>TP53</i> variants according to their likelihood of driving cancer progression or treatment response.

### Impact of this Solution
1. **Improved Prioritization of Variants**: Machine learning models can consider multiple features simultaneously, including variant type, allele frequency, and clinical data, to prioritize <i>TP53</i> variants more accurately. This can help researchers focus their efforts on investigating variants most likely to be clinically relevant.
2. **Identification of Biomarkers**: By identifying <i>TP53</i> variants associated with disease progression or treatment response, this approach can lead to the discovery of biomarkers that could be used for patient stratification, prognosis prediction, and treatment selection, including Personalized Treatment Strategies.

### Data Source
This dataset was obtained from the TP53 website, which contained 80,406 rows and 1,133 columns with no null or duplicate values. The data file used is UMD_mutations_US.csv, available for download at: [https://p53.fr/download-the-database](https://p53.fr/download-the-database).

### Description of the Dataset
- **Mutation Coordinates (Nucleotide)**
  - **HG38_Start**: Start coordinates of the mutation using CRCh38 as reference.
  - **Mutant_Codon**: Sequence of the mutated codon.
- **Mutation Type and Origin**
  - **Variant_Type**: Variant type (SNP, DNP, TNP, INS, DEL).
- **Disease and Sample Information**
  - **Disease**: Name of the disease associated with the mutation.
- **Pathogenicity (Target Feature)**
  - **Pathogenicity**: Standard terminology for TP53 variants (e.g., 'pathogenic', 'likely pathogenic', 'uncertain significance', 'likely benign').

### Project Workflow
1. Data Cleaning and Categorical Reduction
2. Data Visualization
3. Feature Engineering using One Hot Encoding
4. Modeling Selection
5. Model Evaluation
6. Model Optimization

### Machine Learning Model: Random Forest with Cross-Validation and Grid Search
To address the classification task of TP53 variant pathogenicity, we employ a Random Forest model, a powerful ensemble learning technique that combines multiple decision trees to improve predictive performance. Random Forests are well-suited for this task due to their ability to handle complex datasets with high dimensionality and non-linear relationships between features.

#### Cross-Validation
Cross-validation is a crucial technique used to assess the generalization performance of our model. By splitting the dataset into multiple subsets and training the model on different combinations of these subsets, we can evaluate its performance across various data partitions. This helps us to mitigate issues such as overfitting and ensures that our model performs well on unseen data.

#### Grid Search for Hyperparameter Tuning
Hyperparameters play a critical role in the performance of machine learning models. To optimize the performance of our Random Forest classifier, we utilize grid search, a technique that exhaustively searches through a specified subset of hyperparameters to identify the combination that yields the best performance. This iterative process helps us fine-tune the model's parameters, such as the number of trees in the forest, maximum depth of the trees, and the minimum number of samples required to split a node, among others.

By leveraging cross-validation and grid search, we aim to build a robust and accurate classification model for predicting the pathogenicity of TP53 variants. This approach allows us to effectively utilize the available data and optimize the model's performance, ultimately contributing to our understanding of the oncogenic impact of TP53 variants and aiding in the development of personalized treatment strategies for cancer patients.

### Model Evaluation
The baseline modeling was performed with logistic regression and random forest. The initial baseline random forest had a better accuracy than the logistic regression model. It was determined that the features used for modeling were not able to capture the mutations effectively, leading to feature engineering, which improved the performance of the best random forest model to 93%.

### Deployed Model
The model with the highest accuracy is deployed at the following link: [PathFinder Model Deployment](https://capstone-project-pathfinder.streamlit.app/)

### Next Steps and Challenges
- Predict the variants of different genes most commonly occurring in Cancer.
- Create another app that helps researchers and clinicians identify commonly occurring pathogenic variants versus non-pathogenic ones.

---

