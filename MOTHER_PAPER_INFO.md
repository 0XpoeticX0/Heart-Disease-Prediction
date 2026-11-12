# Mother Paper Identification & Printing Guide

## Selected Research Paper
* **Paper Title:** *Analyzing the impact of feature selection methods on machine learning algorithms for heart disease prediction*
* **Authors:** Zeinab Noroozi, Azam Orooji, & Leila Erfannia
* **Journal:** *Scientific Reports* (Nature Portfolio / Springer Nature)
* **Volume:** 13
* **Article Number:** 22588
* **Publication Date:** December 20, 2023
* **DOI:** [10.1038/s41598-023-49962-w](https://doi.org/10.1038/s41598-023-49962-w)
* **PubMed Central (PMC):** [PMC10730875](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10730875/)
* **Journal Impact / Tier:** Q1 Journal, High-Impact SCIE Index

---

## Official Links for Viewing & Printing
1. **Publisher Official Article (Nature Portfolio):**  
   https://www.nature.com/articles/s41598-023-49962-w
2. **Direct Official PDF Download (Free Open Access):**  
   https://www.nature.com/articles/s41598-023-49962-w.pdf
3. **PubMed Central Full Text & PDF Backup:**  
   https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10730875/pdf/41598_2023_Article_49962.pdf

---

## Instructions for Printing for Your Pre-Defense
1. Open the PDF link above in your browser or Adobe Acrobat.
2. Print the full article in double-sided format (or pages 1 to 10 covering Abstract, Methodology, Table 2, Table 4, and Table 6).
3. **Highlight Table 6:** On the printed copy, bookmark **Table 6 ("Performance result comparison before and after feature selection")** so you can immediately show the examiners the exact numbers we replicated (SVM Baseline: 83.17%, Feature Selected: 85.48%, J48 Boost: +3.88%).

---

## Abstract Summary
Cardiovascular disease remains the leading cause of global mortality. Clinical diagnostic datasets often contain redundant and noisy biological attributes that degrade the predictive performance of automated screening systems. This study comprehensively evaluated 16 feature selection methods across 7 machine learning algorithms (SVM, Random Forest, Naïve Bayes, Decision Trees, Logistic Regression, etc.) using the UCI Cleveland Heart Disease dataset. The authors proved that feature selection enhances diagnostic accuracy (reaching 85.5% with SVM and filter methods, and boosting Decision Tree accuracy by +3.88%) while reducing computational complexity.

---

## Benchmark Dataset
* **Dataset Name:** Heart Disease Database (Cleveland Collection)
* **Repository:** UCI Machine Learning Repository
* **Repository Link:** https://archive.ics.uci.edu/dataset/45/heart+disease
* **Samples:** 303 patient records
* **Attributes:** 13 clinical physiological attributes (age, sex, chest pain type, resting BP, serum cholesterol, fasting blood sugar, ECG, maximum heart rate, exercise angina, ST depression, slope, colored fluoroscopy vessels, thallium heart scan)
* **Target:** Heart Disease Status (0: Healthy, 1: Presence of CAD)
