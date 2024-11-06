# Bioactivity-Prediction-App

Bioactivity Prediction App is a machine learning-based tool designed to predict the bioactivity of compounds using data from the ChEMBL Database. This app leverages data preprocessing, feature engineering, and advanced regression techniques to predict the pIC50 values of compounds, providing insights into their potential bioactivity.

Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Setup and Installation](#setup-and-installation)
- [Usage](#usage)
- [Modeling Approach](#modeling-approach)
- [Acknowledgments](#acknowledgments)

## Project Overview

This repository hosts a Streamlit app designed to predict the bioactivity of compounds in inhibiting the enzyme Acetylcholinesterase. Acetylcholinesterase is an important target in Alzheimer's disease research, and this app enables users to upload molecular data, calculate descriptors, and predict bioactivity in terms of pIC50 values using machine learning models.

## Features

- Molecular Descriptor Calculation: Calculates molecular descriptors using PaDEL-Descriptor software.
- Feature Selection: Removes low-variance descriptors, resulting in a refined set of descriptors.
- Machine Learning Prediction: Uses a pre-trained regression model to predict the pIC50 values of uploaded molecular compounds.
- Data Upload: Allows users to upload molecular data file.
- Data Download: Allows users to download prediction results as a CSV file.
- User-Friendly Interface: Built with Streamlit, providing a simple and intuitive interface.

## Tech Stack

- Programming Language: Python
- Libraries: Pandas, Scikit-Learn, RDKit, NumPy, Matplotlib, Seaborn, XGBoost, LightGBM
- Database: ChEMBL Database (external)
- PaDEL-Descriptor (Java-based)

## Project Structure
```bash
├── Bioactivity_Prediction_App
│   ├── app.py                 # Main Streamlit app
│   ├── best_model.pkl         # Pre-trained model file
│   ├── descriptor_list.csv    # List of descriptors used in model training
│   ├── example_acetylcholinesterase.txt  # Example input file
│   ├── logo.png               # Logo image for the app
│   ├── Computational_Drug_Discovery_Project.ipynb  # Python file 
│   └── PaDEL-Descriptor       # PaDEL-Descriptor JAR file for descriptor calculations
│   └── result                 # All the result files are stored here
```

## Setup and Installation

1. Clone the repository:
   ``` bash
   git clone https://github.com/amruthak03/Bioactivity_Prediction_App.git
   cd Bioactivity_Prediction_App
2. Install dependencies:
   ``` bash
   pip install -r requirements.txt
3. Run the app:
   ``` bash
   streamlit run app.py

## Usage

1. Upload a File: In the sidebar, upload your molecule data as a .txt file (example file provided).
2. Descriptor Calculation:  The app will calculate molecular descriptors using PaDEL-Descriptor and removes low-variance descriptors, displaying them in the app.
3. View and Download Predictions: Once descriptors are calculated, the model predicts pIC50 values, displaying them in the app. Results can be downloaded as a CSV file.

## Modeling Approach

- Feature Engineering: Calculated Lipinski descriptors, molecular descriptors (PaDEL) and filtered low-variance descriptors.
- Model Comparison: Compared models including Random Forest, Gradient Boosting, XGBoost, and LightGBM, and selected the best-performing model.
- Hyperparameter Tuning: Used GridSearchCV for fine-tuning the model to optimize performance.
- Final Model: The final model used in this app was saved as best_model.pkl for making predictions.

## Acknowledgements

- Descriptor calculations were performed using [PaDEL-Descriptor](https://onlinelibrary.wiley.com/doi/10.1002/jcc.21707).
- ChEMBL Database for providing valuable bioactivity data.
- RDKit for tools to process molecular structures and compute descriptors.
- Scikit-Learn for model training and evaluation.
