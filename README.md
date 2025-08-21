# AutoML-for-Cardiovascular-Disease-Prediction-Bridging-AI-and-Clinical-Practice
PyCaret, AutoGluon and FLAML with XAI for cardiovascular disease prediction
# Cardiovascular Disease Prediction using AutoML

This project demonstrates the use of several Automated Machine Learning (AutoML) frameworks to predict the presence of cardiovascular disease (CVD) based on a patient's health records. The goal is to compare the performance of different AutoML tools and use Explainable AI (XAI) techniques to understand the model's predictions.

## Project Workflow

The analysis follows these key steps:
1.  **Data Loading and EDA:** The heart disease dataset is loaded and initial exploratory data analysis is performed to understand its structure and distributions.
2.  **Train-Test Split:** The data is split into training (80%) and testing (20%) sets, using stratification to maintain the same proportion of heart disease cases in both sets.
3.  **AutoML Model Training:** Three popular AutoML libraries are used to train and evaluate predictive models on the training data:
    * **PyCaret:** `compare_models()` is used to quickly train and rank a wide variety of classification models.
    * **FLAML:** A lightweight and efficient AutoML library from Microsoft is used to find a high performing model with a given time budget.
    * **AutoGluon:** A powerful AutoML framework from Amazon that trains and stacks multiple models to achieve state-of-the-art performance.
4.  **Explainable AI (XAI):** The best model found by FLAML (XGBoost) is analyzed using the **SHAP** (SHapley Additive Explanations) library to determine global feature importance and understand how individual features impact predictions.
5.  **Feature Selection:** Based on the SHAP analysis, the model is retrained using only the top 10 most important features to see if performance can be maintained or improved with a simpler model.

## Key Libraries & Tools

* **Data Handling:** Pandas
* **Machine Learning:** Scikit-learn
* **AutoML Frameworks:** PyCaret, FLAML, AutoGluon
* **Explainable AI (XAI):** SHAP
* **Data Visualization:** Matplotlib, Seaborn

## Results Summary

* **AutoGluon** achieved the highest accuracy on the unseen test data with **89.13%**.
* **FLAML** found an XGBoost model with an accuracy of **86.96%**.
* The **Explainable AI** analysis with SHAP identified `ST_Slope_Up`, `ChestPainType_ASY`, and `ExerciseAngina_Y` as the most influential features.
* The feature selection experiment showed that retraining an XGBoost model with **only the top 10 features** resulted in an improved accuracy of **90.21%**, suggesting that a simpler, more interpretable model can outperform one trained on all features.

## How to Run This Project
 **Install the required libraries:**
    ```bash
    pip install pandas matplotlib seaborn scikit-learn pycaret shap flaml autogluon --quiet
    ```
2.  **Dataset:**
    Make sure the dataset file `heart_disease.csv` is available in the location specified within Github.

4.  **Run the Jupyter Notebook:**
    Launch Jupyter Notebook and open `CVD_prediction_.ipynb` to execute the cells.


    ## AI Acknowledgement

AI was used to build the first version of the code, including setting up AutoML models and running training and testing steps. We then checked, tested, and changed the code ourselves to make sure it worked correctly for our dataset. AI also helped us fix errors (like Python version issues with PyCaret) and clean up repeated or unnecessary code. AI was used to verify output from SHAP. AI suggested me to use top 6 features, based on that output we checked we dedcided to use top 10 features.
