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
```

-------------

## How to run the project locally
This guide will walk you through setting up your environment and running the “ML in Finance I: Case Study – Forecasting Tax Avoidance Rates” project on your machine.

### 🎯 Goal

- Clone the example project repository  
- Install the required tools and dependencies  
- Launch the environment using **UV**
- Run experiments

### 🛠️ Prerequisites

1. **Python**  
   Download and install the latest version:  
   https://www.python.org/downloads/

2. **Git**  
   Needed to clone the repository:  
   https://git-scm.com/downloads

3. **Ultralight Versioner (UV)**  
   A lightweight Python version & environment manager:  
   https://astral.sh/uv

4. **Your favorite IDE**, e.g. **Visual Studio Code**  
   https://code.visualstudio.com/

### 📥 Installation Steps

#### 1. Install Python
- Visit https://www.python.org/downloads/  
- Download the installer for your OS and follow the instructions.

#### 2. Install Git
- Visit https://git-scm.com/downloads  
- Download and install Git.

#### 3. (Optional) Install Visual Studio Code
- Visit https://code.visualstudio.com/  
- Download and install the editor.

#### 4. Install UV

> **What is UV?**  
> UV (Ultralight Versioner) is a tool to manage multiple Python versions and create isolated project environments. It makes installing dependencies, syncing environments, and switching contexts effortless.

* **macOS / Linux**

  ```bash
  curl -LsSf https://astral.sh/uv/install.sh | sh
  ```

  This command downloads and installs the `uv` CLI tool.

* **Windows (PowerShell)**

  ```powershell
  powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
  ```

  This PowerShell command fetches and executes the `uv` installation script.


---

### 🚀 Project Setup

1. Open your terminal (or PowerShell on Windows).

2. Navigate to your Desktop:

   ```bash
   cd ~/Desktop
   ```

   **What this does:** Changes the working directory to your Desktop.

3. Create a new folder for this tutorial:

   ```bash
   mkdir tutorial_m1
   ```

   **What this does:** Creates a directory named `tutorial_m1`.

4. Enter the tutorial directory:

   ```bash
   cd tutorial_m1
   ```

5. Clone the project repository:

   ```bash
   git clone https://github.com/michaelwozniak/ML-in-Finance-I-case-study-forecasting-tax-avoidance-rates.git
   ```

   **What this does:** Downloads a local copy of the project’s code.

6. Change into the project folder:

   ```bash
   cd ML-in-Finance-I-case-study-forecasting-tax-avoidance-rates/
   ```

7. Sync the environment with UV:

   ```bash
   uv sync
   ```

   **What this does:**

   * Reads the UV configuration (e.g., `uv.yaml` or `pyproject.toml`)
   * Installs all specified dependencies (e.g., pandas, scikit-learn)
   * Creates a Python virtual environment with the correct version

---

## 🔗 Useful Links

* **Project Repository**
  [https://github.com/michaelwozniak/ML-in-Finance-I-case-study-forecasting-tax-avoidance-rates](https://github.com/michaelwozniak/ML-in-Finance-I-case-study-forecasting-tax-avoidance-rates)

* **Python Downloads**
  [https://www.python.org/downloads/](https://www.python.org/downloads/)

* **Git Downloads**
  [https://git-scm.com/downloads](https://git-scm.com/downloads)

* **Visual Studio Code**
  [https://code.visualstudio.com/](https://code.visualstudio.com/)

* **UV (Ultralight Versioner)**
  [https://astral.sh/uv](https://astral.sh/uv)

---

> Good luck and happy learning! 🚀
> If you run into any issues, please open an Issue on the repository or ask your instructor.
-------------

**Attention! This project is for demonstration purposes, i.e. we omit many practices of writing good code and project structuring due to its demonstrative character. It has rather experimental form!!!**
