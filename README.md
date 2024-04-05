<a name="readme-top"></a>
<!-- PROJECT SHIELDS -->
<br />
<div align="center">
  <a href="https://github.com/allyvaz/Capstone-project">
    <img src="https://microbenotes.com/wp-content/uploads/2023/05/Alleles.jpg" alt="Logo" width="80" height="80">
  </a>

<h1 align="center">PathFinder: Unraveling <i>TP53</i> Variant Pathogenicity for Clinical Insights</h1>

  <p align="center">
    <h2>Project Overview</h2>
  </p>
  <p>
  </p><br><h3>Areas of Interest:</h3> 
    <br/>1. Variants of <i>TP53</i> causing Cancer.
    <br/>2. Variant allele frequency of <i>TP53</i>.
    <br/>3. Longitudinal study of <i>TP53</i> variants.
    <br/>4. Exploration of <i>TP53</i> variant interactions with other genes</br> or pathways implicated in Cancer development.
  </p>
  <p align = 'justify'>
    <h3>Problem Statement: </h3>
    <br/>In the realm of cancer research, accurately identifying mutations (also known as variants) from next-generation sequencing of tumor samples poses a significant challenge. Variants exhibit diverse characteristics within the dataset, and both biological and technical variability complicate the process for variant callers. Various metrics, such as sequencing depth around the variant, the count of reads supporting the reference or mutated allele, the quality associated with these reads, and the confidence level of the tools in making specific calls, are crucial for assessing variants. This project will specifically explore the utility of one such metric: Variant Allele Frequency (VAF), in addressing these challenges.
    <br/><h3>Proposed Data Science strategy:</h3>
    <br/> 1. Prioritize <i>TP53</i> variants based on their predicted functional impact, frequency in the dataset, and relevance to pathogenesis.
    <br/>2. Utilize machine learning algorithms, such as random forests, to rank  <i>TP53</i> variants according to their likelihood of driving breast cancer progression or treatment response. 
  </p>
    <br/><h3>Impact of this solution:</h3>
    <br/>1. Improved Prioritization of Variants: Machine learning models can consider multiple features simultaneously, including variant type, allele frequency, and clinical data, to prioritize <i>TP53</i> variants more accurately. This can help researchers focus their efforts on investigating variants most likely to be clinically relevant.
    <br/>2. Identification of Biomarkers: By identifying <i>TP53</i> variants associated with disease progression or treatment response, this approach can lead to the discovery of biomarkers that could be used for patient stratification, prognosis prediction, and treatment selection like Personalized Treatment Strategies. 
    </br><h3>Data Source:</h3>
    </br>This datset was obtained from the TP53 website which contained 80406 rows and 1133 columns. There were no null or duplicate values.
    <br/>Tumor variants in human tumor samples (data file) UMD_mutations_US.csv  
    </br><u>https://p53.fr/download-the-database</u> 
  </p>

  <p>
    <br/><h3>Description of the dataset used in this project</h3>
    <br/><b>Mutation Coordinates (Nucleotide)</b>
    </br>- <b>HG38_Start</b>: Start coordinates of the mutation using CRCh38 as reference.
    </br>- <b>Mutant_Codon</b>: Sequence of the mutated codon.
    <br/><b>Mutation Type and Origin</b>
    </br>- <b>Variant_Type</b>: Variant type (SNP, DNP, TNP, INS, DEL).
    <br/><b>Disease and Sample Information</b>
    </br>- <b>Disease</b>: Name of the disease associated with the mutation.
    <br/><b>Pathogenicity (Target Feature)</b>
    </br>- <b>Pathogenicity</b>: Standard terminology for TP53 variants (e.g., 'pathogenic', 'likely pathogenic', 'uncertain significance', 'likely benign').
  </p>
   
  <p>
    <h3><b>Project Workflow</b></h3>
    </br>1. Data Cleaning and Categorical reduction
    </br>2. Data Visualization
    </br>3. Feature Engineering using One hot encoding
    </br>4. Modeling Selection
    </br>5. Model Evaluation
    </br>6. Model Optimization
    </br><h3>Machine Learning Model: Random Forest with Cross-Validation and Grid Search</h3>
    </br>To address the classification task of TP53 variant pathogenicity, we employ a Random Forest model, a powerful ensemble learning technique that combines multiple decision trees to improve predictive performance. Random Forests are well-suited for this task due to their ability to handle complex datasets with high dimensionality and non-linear relationships between features.
    </br><h3>Cross-Validation</h3>
    </br>Cross-validation is a crucial technique used to assess the generalization performance of our model. By splitting the dataset into multiple subsets and training the model on different combinations of these subsets, we can evaluate its performance across various data partitions. This helps us to mitigate issues such as overfitting and ensures that our model performs well on unseen data.
    </br><h3>Grid Search for Hyperparameter Tuning</h3>
    </br>Hyperparameters play a critical role in the performance of machine learning models. To optimize the performance of our Random Forest classifier, we utilize grid search, a technique that exhaustively searches through a specified subset of hyperparameters to identify the combination that yields the best performance. This iterative process helps us fine-tune the model's parameters, such as the number of trees in the forest, maximum depth of the trees, and the minimum number of samples required to split a node, among others.
    </br>By leveraging cross-validation and grid search, we aim to build a robust and accurate classification model for predicting the pathogenicity of TP53 variants. This approach allows us to effectively utilize the available data and optimize the model's performance, ultimately contributing to our understanding of the oncogenic impact of TP53 variants and aiding in the development of personalized treatment strategies for cancer patients.     
    </br><h3>Model Evaluation</h3>
    </br>The baseline modeling was performed with logistic regression and random forest.The inital baseline random forest had a better accuracy than the log reg model. It was also determined that the features used for modeling were not able to capture the mutations and hence feature engineering was performed and the performance of the best random forest model was 93%.
    </br><h3>Deployed model</h3>
    </br> The model with the highest accuracy is deployed on the following link:
    </br> https://capstone-project-pathfinder.streamlit.app/
    </br></br><b>Next Steps and Challenges</b>
    </br>To try predict the variants of different genes most commonly occurring in Cancer and create another app that helps researchers and clinicians look for commonly occurring pathogenic variants versus non-pathogenic ones.
  </p>
