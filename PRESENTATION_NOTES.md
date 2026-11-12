# Presentation Notes & Examiner Defense Guide
**Student / Presenter:** Rahi  
**Project:** Machine Learning Reproduction of Nature Portfolio (*Scientific Reports*, 2023) Paper  
**Mother Paper:** *Analyzing the impact of feature selection methods on machine learning algorithms for heart disease prediction* (DOI: 10.1038/s41598-023-49962-w)

---

## 🎤 Slide-by-Slide Speaker Script (5 to 8 Minutes Delivery)

### Slide 1: Title Slide
> *"Respected teachers and committee members, good afternoon. Today I will present my machine learning reproduction and comparative study. For this work, I selected a peer-reviewed research paper published in Nature Portfolio's Scientific Reports in December 2023 titled 'Analyzing the impact of feature selection methods on machine learning algorithms for heart disease prediction'. I replicated their entire pipeline using their exact benchmark dataset, reproduced their experiments using 10-fold stratified cross-validation, and compared our empirical results directly with the published findings."*

### Slide 2: Mother Paper Overview & Citation
> *"The mother paper is authored by Zeinab Noroozi and colleagues, published in Scientific Reports, Volume 13, indexed in PubMed Central under PMCID 10730875. I have the printed copy of the original published paper here with Table 6 bookmarked for your review. The paper addresses a vital clinical problem: coronary artery disease screening using non-invasive clinical attributes."*

### Slide 3: Benchmark Dataset Profile
> *"The study uses the gold-standard UCI Cleveland Heart Disease dataset, comprising 303 patient records with 13 physiological features—such as chest pain type, exercise ST depression, maximum heart rate, and fluoroscopy colored vessels. There are 164 healthy cases and 139 heart disease cases. I preprocessed the data by handling the 6 missing values via median and mode imputation and binarizing the target variable."*

### Slide 4: Experimental Methodology & Architecture
> *"To ensure rigorous, leak-free evaluation, I implemented a 10-fold stratified cross-validation protocol. Crucially, feature scaling was conducted inside each fold on the training partition only and then applied to the validation partition to prevent data leakage. I implemented 6 core machine learning classifiers matching the paper: Support Vector Machine, Random Forest, Naïve Bayes, Decision Trees, Logistic Regression, and Multi-Layer Perceptrons."*

### Slide 5: Feature Selection Engineering
> *"In accordance with the paper, I evaluated both filter methods—such as Information Gain and Correlation-based Feature Selection—and wrapper methods. Our information gain analysis revealed that thallium scan results, major vessels, chest pain, and ST depression hold the highest mutual information. Features like fasting blood sugar and cholesterol exhibited substantial noise. We extracted an optimal 8-feature subset."*

### Slide 6: Side-by-Side Benchmark & Comparison
> *"Here is the most critical slide: our direct side-by-side comparison with the mother paper's Table 6.
> Notice our baseline accuracy alignment:
> • Our Support Vector Machine baseline achieved 83.13%, which matches the paper's 83.17% with an error of just minus 0.04%.
> • Our Logistic Regression baseline achieved 83.45%, matching the paper's 83.50% with only minus 0.05% difference.
> • Our Naïve Bayes model baseline reached 83.78% compared to the paper's 83.17%.
> • Most importantly, we confirmed the paper's primary thesis: applying feature selection produced a massive +4.31% accuracy boost for single Decision Trees (rising from 75.84% to 80.15%), exactly mirroring the paper's reported +3.88% jump."*

### Slide 7 & 8: Visual Analytics & Confusion Matrices
> *"On these slides, you can see our grouped bar charts, ROC curves, and 10-fold confusion matrices. All models maintain high sensitivity over 80%, meaning our classifiers reliably detect genuine heart disease patients and minimize false negatives."*

### Slide 9 & 10: Conclusion & Laptop Demonstration
> *"In conclusion, our replication successfully verified the mother paper's core claims. I have my laptop open with the fully executed Jupyter Notebook and source code in the `ML_RAHI` folder ready to demonstrate any specific cell or metric live. Thank you, and I look forward to your questions."*

---

## 💡 Anticipated Examiner Questions & Winning Answers

### Question 1: "Why did you use 10-Fold Stratified Cross-Validation instead of a simple 80/20 train/test split?"
* **Answer:** *"With medical datasets of moderate size like 303 samples, a single 80/20 train/test split introduces high variance depending on which specific patient cases end up in the test split. Stratified 10-Fold Cross-Validation ensures every sample is used for both training and testing while preserving the exact 54% healthy to 46% disease ratio across all 10 folds, yielding statistically robust and unbiased performance estimates that directly match the methodology of Noroozi et al. (2023)."*

### Question 2: "Why did the Decision Tree improve by +4.31% after feature selection, but Random Forest barely changed (+0.96%)?"
* **Answer:** *"Single decision trees (CART/J48) suffer from high variance and are greedy algorithms. When noisy or weakly correlated features (like fasting blood sugar and cholesterol) are included, the decision tree can split on them early, creating overfitted branches that fail on unseen validation folds. Stripping these features prunes the hypothesis space. In contrast, Random Forest is an ensemble method that uses bagging and random feature subspace sampling at every split; this inherent mechanism naturally cancels out noise and prevents single features from dominating, making it intrinsically resilient to redundant features."*

### Question 3: "How did you prevent data leakage during preprocessing?"
* **Answer:** *"A common mistake in ML papers is applying standard scaling on the entire dataset before cross-validation. In our implementation (located in `src/evaluation.py`), we fit the `StandardScaler` strictly on the 9 training folds and then use `scaler.transform()` on the 10th validation fold inside each fold iteration. This guarantees zero information from validation folds leaks into the model training pipeline."*

### Question 4: "Why did Naïve Bayes achieve such a high accuracy (85.44%) after feature selection?"
* **Answer:** *"Naïve Bayes makes the fundamental assumption of class-conditional feature independence. Real-world continuous features like blood pressure, cholesterol, and age often have overlapping collinearity. By removing the redundant and noisy continuous features, we reduce the degree of independence violation, allowing the Bayesian likelihood estimations to align much better with clinical outcomes."*

### Question 5: "Where can we verify the dataset and mother paper?"
* **Answer:** *"The dataset is directly from the UCI Machine Learning Repository (Heart Disease Cleveland database), stored locally under `ML_RAHI/dataset/heart_disease_cleveland.csv`. The mother paper is published in Nature Portfolio's Scientific Reports, Volume 13 (2023), DOI: 10.1038/s41598-023-49962-w, and I have the printed copy right here."*
