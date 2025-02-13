# unibs_mldm_diabetes

Project for the Machine Learning &amp; Data Mining course, held at Università degli Studi di Brescia (Italy).

All training data has been taken from the [Diabetes 130-US Hospitals for Years 1999-2008](https://archive.ics.uci.edu/dataset/296/diabetes+130-us+hospitals+for+years+1999-2008) UCI dataset.

## Environment Setup

To use the program, you first need to have Python 3.12 or more recent installed, and all the necessary libraries.

It is highly recommended to follow the same steps described in the [CONTRIBUTING.md](./CONTRIBUTING.md) file, where you create a virtual environment specific to this project, so that all dependencies will only impact the project itself.

If you don't mind, assuming you already have Python on your system, to download all dependencies you just need to execute the following:

```bash
pip install -r requirements.txt
```

## How To Use

### Dataset files

The [data](./data/) folder contains two subfolders. In the [original](./data/original/) subfolder you can find:

- The original dataset (`diabetic_data.csv`).
- The ID codes and associated meanings used in the dataset for some features (`admission_source_ids.csv`, `admission_type_ids.csv`, `discharge_disposition_ids.csv`).

In the [processed](./data/processed/) subfolder you can find:

- The resulting dataset after preprocessing (`diabetic_data_cleaned.csv`).
- The training set (`train.csv`) and testing set (`test.csv`) generated after feature selection.

### Notebook files

The [notebooks](./notebooks/) folders contains all Jupiter notebooks used for the project. In particular:

- The notebook used for applying the preprocessing to the entire original dataset (`dataset_eda.ipynb`). This should be run first.
- The notebook used for doing feature selection on the preprocessed dataset (`feature_selection.ipynb`). This should be the second step, right after the preprocessing.
- All notebooks used for doing hyperparameter-tuning on different models (`tuning_{*}.ipynb`).

> If you want to follow the same steps applied by us during the project, it is recommended to execute the notebooks in the given order.

### Optuna files

In the [optuna](./optuna/) folder, as you execute the model tuning notebooks, their respective subfolders are created, with all hyperparameter search logging. More specifically:

- Logging for tuning without any resampling (`optuna_{*}_none.log`).
- Logging for tuning using random undersampling (`optuna_{*}_rus.log`).
- Logging for tuning using SMOTE resampling (`optuna_{*}_smote.log`).
- Logging for tuning using SMOTE + Tomek Links resampling (`optuna_{*}_smote-tomek.log`).

> Different resampling techniques were used, since the dataset itself was heavily imbalanced, thus requiring some type of resampling.
