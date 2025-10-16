# Solar Flares Classification Project
## Prerequisites
- Python 3.8 or higher
- Jupyter Notebook
- Libraries:
  - Seaborn
  - Matplotlib
  - Numpy
  - Scikit-learn
  - Pytorch
  - Pandas
  - Tensorflow
  - Notebook

To install these modules please make sure to follow these steps:

**- On windows:**

First check the version of the installed python
  ``` bash
python --version

``` 
and then download the new python version using this [link](https://www.python.org/downloads/).

**- On MacOs:**
``` bash
brew update
brew install python
python3 --version
```

After that, download the requirements.txt file found above and import these libraries using:

```bash
pip install -r requirements.txt
```
## To clone the repository:
```bash
git clone https://github.com/mhmdsharafeddine/EECE490Project.git
cd EECE490Project

```

## Overview
This project aims to predict solar flare intensity using machine learning models trained on features extracted from magnetogram images of solar active regions.
Solar flares are categorized into four main classes based on their intensity: C, M, X, and 0 (no flare).
Our objective is to identify patterns in solar magnetic data that help forecast flare strength accurately.

## Dataset
The dataset used is Active region magnetograms for solar flare prediction: Full resolution dataset documented on Dryad and it can be found on this [link](https://datadryad.org/dataset/doi:10.5061/dryad.dv41ns23n). 

For our work, we will focus on the Validation_data_by_AR.csv file, which contains pre-processed features extracted from solar active regions (ARs). Each row represents a single active region, while columns describe numerical measurements derived from magnetogram images captured by the SDO/HMI instrument.

This file includes a total of 759,436 records and 31 features grouped into several categories:

| Gradient features  | Neutral line features         | Wavelet features          | Flux features            | Flare class         | Image path                |
|--------------------|------------------------------|---------------------------|---------------------------|---------------------|---------------------------|
| Gradient mean      | NL length                    | Wavelet energy level 1    | Total unsigned flux       | Binary flare class  | Path to image in dataset  |
| Gradient std       | NL no. fragments             | Wavelet energy level 2    | Total signed flux         |                     |                           |
| Gradient median    | NL gradient-weighted length  | Wavelet energy level 3    | Total negative flux       |                     |                           |
| Gradient min       | NL curvature mean            | Wavelet energy level 4    | Total positive flux       |                     |                           |
| Gradient max       | NL curvature std             | Wavelet energy level 5    |                           |                     |                           |
| Gradient skewness  | NL curvature median          |                           |                           |                     |                           |
| Gradient kurtosis  | NL curvature min             |                           |                           |                     |                           |
|                    | NL curvature max             |                           |                           |                     |                           |
|                    | NL bending energy std        |                           |                           |                     |                           |
|                    | NL bending energy median     |                           |                           |                     |                           |
|                    | NL bending energy min        |                           |                           |                     |                           |
|                    | NL bending energy max        |                           |                           |                     |                           |

## Data exploration

The dataset was explored to understand its structure, feature behavior, and class balance. An initial analysis showed that non-flare events dominate the data, leading to class imbalance. To handle this, flare strengths were grouped into four main categories (0, C, M, and X), with potential rebalancing through SMOTE in later stages.

Feature variance, correlation, and mutual information analyses helped identify the most relevant predictors for solar flare classification. High-variance and strongly correlated features were found to carry the most information about flare strength, confirming that the dataset provides a strong foundation for model training.

Further details and visualizations are available in the EECE490ProjectData.ipynb notebook.


## Model Training Plan

Our training process follows a step-by-step approach to ensure a clear understanding of each model, its purpose, and the reason it was chosen. The following two models have been implemented before but we will go ahead establish these models to visualize the accuracies and prediction scores:

**- Baseline – Support Vector Machine (SVM):**

We begin with an SVM trained on the 29 extracted magnetic features to set a baseline. This model helps us understand how well linear decision boundaries perform on our data and establishes a reference point for future comparisons.

**- Ensemble Models – Random Forest and XGBoost:**

After the baseline, we move to ensemble models to explore nonlinear relationships between features. These models help us see how combining multiple decision trees can improve accuracy and reveal which magnetic parameters have the strongest impact on flare prediction.

After that we will implement new models such as:

**- Neural Network**

We plan to train aa neural network to study how deeper architectures can capture complex feature interactions and subtle variations between flare categories. This step allows us to compare traditional models with deep learning approaches and understand their trade-offs.

**- Decision Tree**

We plan to train a Decision Tree model to establish a simple model for solar flare classification. This will help us understand which magnetic features contribute most to flare prediction and provide a foundation for comparing more advanced ensemble and boosting models.


This is a preliminary proposal, and we will continue experimenting with additional models throughout the project. The goal is to compare their performance, interpretability, and generalization ability before finalizing the best approach.

Each model will be evaluated using accuracy, precision, recall and F1-score. 


