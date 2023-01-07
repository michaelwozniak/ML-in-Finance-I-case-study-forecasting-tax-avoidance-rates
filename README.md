# ML in Finance I - case study *Forecasting tax avoidance rates*

## Introduction to the project

### Economic background
**Tax avoidance is not a crime!** Companies that carry out this act are on the verge of law. By definition: tax avoidance consists in carrying out economic activities in such a way that they are understood in a different way from tax regulations, in order to reduce the tax burden. International tax avoidance arose as a result of globalization and liberalization of economic systems of countries, weakening trade barriers and development of new technologies. Tax avoidance is achieved through aggressive **tax optimization** (e.g. tax havens, double taxation agreements, etc.). 

### Goal of the project
In this study, we will check whether we can **forecast for one year ahead the level of tax avoidance by a group of companies** listed on stock exchanges using shallow Machine Learning models. As the econometric research shows, this problem is non-trivial, and the most important determinants result from the financial statements per se. The question arises whether any additional data sources can be used to forecast this problem. Forecasting such a phenomsenon may be particularly important for the tax authorities and legislators. It helps to create rules that would fight against tax avoidance!

### Extra key information
There are many ways in the literature to measure tax avoidance. All of them have their advantages and disadvantages. However, the most popular metric appears to be Effective Tax Rate (ETR) = $\dfrac{\textrm{total tax expenses}}{\textrm{pre-tax income}} $. Due to this formula, ETR has values in the range [0,1]. This measure applies directly to each jurisdiction and it is based on annual data published in the financial statements and this involves an annual change in the effective tax rate, or failure to determine it, in the case of negative income tax resulting from current tax overruns of deferred tax assets. ETR will be used as the target/endogenous variable in this study. Therefore, the following evaluation metrics for the given problem were selected: Mean Absolute Error (MAE), Root Mean Square error (RMSE). The choice was not accidental: MAE allows for relatively easy interpretation, while RMSE punishes model for large individual errors, which in the case of ETR forecasting may be crucial. For this case, absolute measures seem to be a more correct approach than relative ones. Nevertheless, the most important metric will be RMSE.

This problem is a classic panel problem (many companies and many years).

-------------

## Project structure
```
├── README.md
├── data
│   ├── input
│   ├── models_output
│   └── output
├── models
├── notebooks
│   ├── 01. project-description-&-data-preparation-&-EDA.ipynb
│   ├── 02. feature-engineering-&-feature-selection.ipynb
│   ├── 03.naive-model.ipynb
│   ├── 04.ols-model.ipynb
│   ├── 05.arma-model.ipynb
│   ├── 06.ardl-model.ipynb
│   ├── 07.knn-model.ipynb
│   ├── 08.svr-model.ipynb
│   ├── 09.final-comparison-and-summary.ipynb
│   └── 10.homework-random-forest-model.ipynb
├── requirements.txt
└── requirements_pypi.txt
```

-------------

## How to run the project locally
1. Install **conda** environment management system (if you don't have it - on WNE UW computers it is already installed): https://conda.io/projects/conda/en/latest/user-guide/install/index.html
2. Create **conda environment** using provided requirements.txt file (paste the following commands in Anaconda Prompt): 
    2.0 Navigate in Anaconda Prompt into the project directory, for instance in my case it will be: `cd /Users/michalwozniak/ML-in-Finance-I-case-study-forecasting-tax-avoidance-rates`
    2.1. `conda config --append channels conda-forge`
    2.2. `conda create --name case_study_env --file requirements.txt`
    2.3. `conda activate case_study_env`
    2.4. `pip install -r requirements_pypi.txt`
3. Run the project (using your *case_study_env*) in your favourite IDE which supports notebooks for instance in Jupyter Notebook, for instance run in Anaconda Prompt: 
    3.1 `conda activate case_study_env`
    3.2 `jupyter notebook`
4. Voilà

## How to run the project remotely
1. Log in to your Google account
2. Copy url of this Github project and change the domain from 'github.com' to 'githubtocolab.com'
3. Voilà

-------------

**Attention! This project is for demonstration purposes, i.e. we omit many practices of writing good code and project structuring due to its demonstrative character. It has rather experimental form!!!**