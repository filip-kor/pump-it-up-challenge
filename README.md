# "Pump It Up" Data Science Challenge Solution
By Filip Kornata & Adam Williams

Completed 18/05/2023

## Contents
- [About the Project](#about-the-project)
- [Technologies Used](#technologies-used)
- [Included Files](#included-files)
- [Results](#results)
- [Acknowledgements](#acknowledgements)

## About the Project

This project is based on a [DrivenData competition](https://www.drivendata.org/competitions/7/pump-it-up-data-mining-the-water-table/) and uses data from Taarifa and the Tanzanian Ministry of Water to classify water pumps into three classes: `functional`, `needs repair` and `non-functional`. The data is a mix of human-input and sensor-based information with many irrelevant, duplicate, missing and problematic values. The aim of this project is to optimise maintenance operations and improve water accessibility in Tanzania. Our publicly submitted prediction result was superior to 96% of the entrants.

Our approach improves on [BrendaLoznik's solution](https://github.com/BrendaLoznik/waterpumps/tree/main) by extending all of the existing stages and introducing new preprocessing (feature selection, dimensionality reduction) and modelling solutions, improving the predictions' quality. Our implementation includes 4 main elements:
- Exploratory Data Analysis
- Preprocessing
- Modelling
- Research Questions

On top of improving the prediction result, our project also aims to investigate potential causes of poor condition of the pumps. We answered the following four research questions, which identified the conditions and variables, which affect the lifespan of a water pump:
1. What are the main factors associated with pump failure or malfunction, and how do these factors vary across different regions of Tanzania?
2. Which operators and/or management groups have the highest success rates in maintaining water pumps, and how do these rates vary based on factors which may make pump maintenance easier, such as water cost, pump type or location remoteness?
3. What are the interactions between different features, such as water quantity and pump type, which could provide insights into the underlying causes of pump failure?
4. How does the age of a water pump relate to its function- ality, and is there a point at which pumps become significantly more likely to break down or require replacement?

The details of our extensions, research questions and potential areas of future research are explained in the IEEE conference style report [Final-Report.pdf](Final-Report.pdf).

The project was a part of COMP4030 Data Science and Machine Learning module at the University of Nottingham.

## Technologies Used
- Python
- Pandas
- scikit-learn
- Seaborn
- Matplotlib
- Git
- LaTeX

## Included Files
### EDA.ipynb
This notebook contains our Exploratory Data Analysis for the dataset. It contains a range of visualisations and summary statistics, generated with Seaborn, Matplotlib and Pandas.

### Preprocessing.ipynb
This notebook contains our full preprocessing pipeline, including Data Imputation, Feature Engineering, Feature Normalisation/Scaling, Categorical Feature Encoding, Feature Selection, and Dimensionality Reduction.

### Modelling.ipynb
This notebook contains our modelling code, including 12 different classification approaches. scikit-learn used to create classification models.

### Research-Questions.ipynb
This notebook contains code for answering the 5 research questions outlined in our report.

### Final-Report.pdf
This is our final report for the project, in IEEE conference format. The paper was produced using LaTeX. It contains a detailed explanation of our methods and results.

## Results

## Acknowledgements
Thanks to Brenda Loznik for providing her original solution to the project, which our code expanded upon.
