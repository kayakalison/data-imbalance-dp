# data-imbalance-dp
Exploring the impact of data imbalance on ε-Differential Privacy

## Abstract
Differential Privacy (DP) has emerged as a rigorous mathematical framework for use in privacy preserving data mining. While the effects of imbalanced data have been extensively studied in classical Machine Learning (ML), their implications on DP remain largely unexplored. This study examines the impact of class imbalance on the privacy-utility trade-off across three differentially private ML algorithms: Gaussian Naïve Bayes (NB), Logistic Regression (LR), and Random Forest (RF). Using Synthetic Minority Oversampling Technique (SMOTE) it evaluates the performance and privacy sensitivity of these learners at varying levels of imbalance
from <1% to ≈10%. The findings reveal that differentially private LR (DP-LR) offers the best performance but is highly sensitive to privacy, differentially private RF (DP-RF) is the least sensitive to privacy but the most impacted by data imbalance, and differentially private NB (DP-NB) allows for the highest levels of privacy paired with very good performance and low computational overheads even when trained on extremely imbalanced data. This research concludes that DP-NB is the most optimal of the approaches studied in terms of privacy, performance, and computational efficiency when trained on imbalanced data, particularly after addressing the imbalance with SMOTE.

## Introduction
This project explores the impact of data imbalance on ε-Differential Privacy in machine learning algorithms using the diffprivlib library developed by IBM [1]. It includes a set of Jupyter notebooks that demonstrate the findings and methods used in the study.

## Findings
This study revealed the impact of SMOTE on DP and the privacy-utility trade-off point for three ML algorithms commonly used in binary classifications. The results indicate that SMOTE significantly enhances the performance of DP-RF, suggesting that this ensemble method is particularly sensitive to class imbalance. This sensitivity may explain the observed discrepancies between the performances of non-private scikit-learn and DP-RF($\epsilon$ = $\infty$). Additionally, the dramatic performance improvement in NB under DP conditions when combined with SMOTE warrants further investigation. Understanding whether this boost is due to overfitting or other factors remains an open question. While these findings can point research and industry alike using real-world extremely imbalanced datasets ($\pi$ < 1\%) into focusing their initial investigations on NB, they also underscore the necessity for more focused experimentation to determine the repeatability and underlying causes of these interactions. Future research should delve deeper into these aspects to build a comprehensive understanding of the interplay between SMOTE, DP, and ML algorithms, ultimately advancing the field of privacy-preserving data mining.

![Combined results](https://github.com/kayakalison/data-imbalance-dp/blob/main/figures/Combined-Graph2.png)

## Execution Environment
The notebooks were developed and tested in the following environment:
- Jupyter® Notebook running on a Python 3 kernel 

The notebooks require the following packages to be installed:
- Python® == 3.11.9
- pandas == 2.2.1
- numpy == 1.26.4
- matplotlib == 3.8.4
- joblib == 1.4.2
- scikit-learn (sklearn) == 1.4.2
- diffprivlib == 0.6.4
- lilac-arff == 2.5.0
- scipy == 1.11.4
- tqdm == 4.66.4

## Installation Instructions
To set up the required environment, follow these steps:

1. **Create a new execution environment**:
    * In Anaconda Navigator select `Environments` from the main menu bar on the left hand side. 
    * Then select `Create` from the Environments sub-menu at the bottom. 
    * This will launch a `Create new environment` pop-up which will require you to name the environment (i.e. `IRP`) and select 3.11.9 from the `Python` dropdown menu. 
    * Hit `Create`.

2. **Install the public packages using Anaconda**:
    * Select the newly created environment and ensure the dropdown box next to `Channels` is set to `Not installed`.
    * Scroll down (or use the search field) to locate the row for `pandas` version 2.2.1. Click on the `...` to the left of the package then click `Apply` in the bottom right.
    * Repeat for the following publicly available and required packages:
        * `numpy` version 1.26.4 or higher
        * `matplotlib` version 3.8.4 or higher
        * `joblib` version 1.4.2 or higher
        * `scikit-learn` version 1.4.2 or higher
        * `lilac-arff` version 2.5.0 or higher
        * `scipy` version 1.11.4 or higher
        * `tqdm` version 4.66.4 or higher

3. **Install the additional required packages using pip**:
    * Left click on the green arrow to the right of the execution environment and select `Open Terminal`.
    *  Then type:

            pip install diffprivlib

## Usage Instructions
To run the notebooks:

1. **Launch Anaconda Navigator**
2. **Select the created execution environment.**
3. **Select Jupyter Notebook.**
4. **Navigate to the file location where this artefact directory is stored.**
5. **Open and run the notebooks in the following order**:
    1. `Diffprivlib Experiment-NB.ipynb`, approx. processing time: 1.4 hours
    2. `Diffprivlib Experiment-LR.ipynb`, approx. processing time: 4.6 hours
    3. `Diffprivlib Experiment-RF.ipynb`, approx. processing time: 11.5 hours

Note: Running each of these files will over-write the figures in the local figures folder with new, identical versions.

## File Descriptions
- `Diffprivlib Experiment-NB.ipynb`: A Jupyter® notebook containing the NB analysis.
- `Diffprivlib Experiment-LR.ipynb`: A Jupyter®  notebook containing the LR analysis.
- `Diffprivlib Experiment-RF.ipynb`: A Jupyter® notebook containing the RF analysis.
- `datasets`: A folder containing all of the datasets required for reproducibility.
- `figures`: A folder containing all of the figures output by this code.

## Citing this Work
If you use this for research, please consider citing the folowing reference paper:
```
  @mastersthesis{data-imbalance-dp,
  author = {Krauskopf, Alison},
  title = {Exploring the impact of data imbalance on ε-Differential Privacy},
  school = {University of York},
  year = {2024},
  note = {[Unpublished]}
}
```

## References
[1] N. Holohan, S. Braghin, P.M. Aonghusa, and K. Levancher, "Diffprivlib: The IBM differential privacy library," *ArXiv e-prints 1907.02444 [cs.CR]*, 2019. doi: 10.48550/arXiv.1907.02444
