![Project Logo](assets/WSPP_logo.png)

<h1 align="center">
Water Solubility Prediction Project
</h1>

## Overview
This project aims to predict the water solubility of chemical compounds using machine learning techniques. The project developed here can be used to estimate the solubility of new compounds only using the SMILES code of the compounds, which can be valuable in various industries such as pharmaceuticals, agriculture, and environmental science.
In this repository, we are making available the data we used to train and test our models and `.pkl` files containing the optimized parameters of our best model. But more importantly a notebook tracing what we did from the beginning to the end of this project and a package that can predict the water solubility of several SMILEs and of a `.csv` file containing several SMILEs. 

## Project Structure
The project is structured as follows:

**First, a Notebook containing:**
- Import Relevant Modules and Libraries
- Data Collection
- Data Cleaning
- Calculation of RDkit Molecular Descriptors
- Select Machine Learning Models
- Fine-tuning
- Analysis of different models
- Saving of the best trained model and standard scaler

**Second, a Package of two main functions containing:**
-  A function tp predict the LogS value for one or more  SMILES
-  A function to predicts LogS values for SMILES codes stored in a CSV file
 
## Installation
1. Clone this repository:
```
git clone https://github.com/Nohalyan/Projetppchem
```
2. Open your terminal or Anaconda Prompt and navigate to the directory `/src/Projectppchem` containing the `ppchem_environment.yml` file and run the following command to create the Conda environment:
```
conda env create -f ppchem_environment.yml
```
3. Activate the newly created Conda environment:
```
conda activate ppchem_environment 
```

## Usage

### For the Notebook:

1. **Data Preparation:** Place your dataset in the `data/` directory. Ensure the dataset is formatted correctly with features and labels.
2. **Exploratory Data Analysis:** Explore the dataset using the Colab notebooks in the `notebooks/` directory to understand the data distribution and relationships.
3. **Model Training:** Use the scripts in the Colab notebooks in the `notebooks/` directory to preprocess the data, train machine learning models, and save the trained models in the corresponding `models/` directory.
4. **Model Evaluation:** Evaluate the model performance using the evaluation using the scripts in the Colab notebooks in the `notebooks/` directory.
5. **Prediction:** Once trained, the models in the models/ directory can be used to predict the water solubility of new compounds by providing the required input features.
6. 
### For the Package:
First, clone our repos
If you are using a notebook without the environment, you can download the necessary libraries:
```
!pip install pandas numpy rdkit tqdm lightgbm
```

Once the repository has been cloned, you can use the following function to import the functions of our pacakge:
```
from Projectppchem.src.WSPP import wspp_functions as wspp
```

The two main functions of our package are `predict_logS_smiles` and `predict_logS_csv` which can be used in the following way:
```
wspp.predict_logS_smiles(*smiles_codes) and wspp.predict_logS_csv(csv_file_path)
```
The first function `wspp.predict_logS_smiles(*smiles_codes)` can be used to predict the LogS value for one or more SMILES at the same time.
The second fucntion `wspp.predict_logS_csv(csv_file_path)` can be used to predicts LogS values for SMILES codes stored in a CSV file.
And if you need any help, you can use the function `wspp.help()` which will give you more precise information on the functions as well as an example of how to use them. 

## License
This project is licensed under the MIT License.

## References
This project is based on the code of this Github Jupyter notebook: https://github.com/gashawmg, as well as data from https://github.com/PatWalters. 

## Authors
- Cossard Lucas: https://github.com/Nohalyan
- Venancio Enzo: https://github.com/Enzo-vnc

This project was carried out as part of EPFL's Practical programming in Chemistry course.
