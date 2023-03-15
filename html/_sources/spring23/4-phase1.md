# Phase 1: Explore the data

Analyzing NGO data in India in  the existing data sources. This involves reviewing old CSV files and summarizing the content to understand the types of data that are available. This helps gain a deeper understanding of the types of data, common errors, and missing information. Initial cleaning and transformation may be necessary to convert text data into numerical representations, remove stop words, and irrelevant information.

The goal of this exploration is to gain a comprehensive understanding of the data and domain, providing a solid foundation for subsequent steps in the data analysis process and ensuring the analysis is well-informed and accurate.

## Exploring the data

1. Review the Data Dictionary: If available, review the data dictionary to understand the meaning of each variable and the values it can take.
2. Understand the Structure: Understand the structure of the data, including the number of observations, variables, and any missing values.
3. Identify Data Types: Identify the data types of each variable, such as categorical, numerical, or text data.
4. Look for Trends and Patterns: Look for trends and patterns in the data, such as outliers, skewness, or unusual observations.
5. Check for Data Quality Issues: Check for data quality issues, such as missing values, errors, or inconsistencies in the data.
6. Determine the Purpose of the Analysis: Determine the purpose of the analysis and what insights you hope to gain from the data.
Clean and Transform the Data: Clean and transform the data as necessary, such as removing missing values, dealing with outliers, or converting text data into numerical representations.

```{admonition} Data dictionary vs Codebook
:class: dropdown
A data dictionary and a codebook are both documents that provide information about a dataset. However, they have slightly different purposes and contents.

A data dictionary is a reference document that provides definitions and descriptions of the variables in a dataset, including their names, data types, units of measurement, and any relevant constraints. It is meant to help users understand the structure and content of the data.

A codebook, on the other hand, is a comprehensive document that provides detailed information about a dataset, including the background and context of the data collection, the data dictionary, the coding and recoding of variables, and any other information that is relevant to the data analysis. It is meant to provide a complete overview of the data and the steps that were taken to prepare it for analysis.
```

```{admonition} [Codebook](https://github.com/DaanMatch/Codebook)

<img src="img/codebook_example.png" alt="Codebook Example" class="bg-primary mb-1" width="600px">

A codebook is a document that provides detailed information about the variables, data elements, and coding schemes used in a project.

A codebook typically includes information about the variables, such as their names, definitions, measurement scales, missing data codes, and any transformations that have been applied to the data. It may also include information about the data source, the sample size, and any other relevant details about the data.

The purpose of a codebook is to provide a standardized and consistent reference for the data, making it easier for us to understand and use the data correctly.
```

## Tips on Summarizing data

```{admonition} Guide to Effective Graphs
:class: tip
1. Title: Give the histogram a descriptive title that summarizes the main findings of the data. This should be brief, but informative.
2. X and Y Axis Labels: Label the x-axis with the variable that is being plotted, and the y-axis with the frequency or count of the observations.
3. Units: Make sure to include the units of measurement on the axes if applicable.
4. Legend: If the histogram is part of a larger figure with multiple plots, include a legend to help the audience understand what each plot represents.
5. Data Source: If applicable, include a note about the data source, sample size, and date range of the data.
Annotate the Plot: Highlight important features or patterns in the histogram with annotations or lines.
6. Style: Choose colors and styles that are easy to read and clearly convey the information.
```

## Documentation

[Tips on Coding for a Team Project](https://docs.google.com/document/d/19fB5ppzBzdMjTNImoUziohq8d1AB84rDN_DavQGhKAY/edit)

``````{admonition} Documentation Example
:class: dropdown
```
def predict_and_score(model, X, y):
    """
    Function that performs classification using model while using ROC AUC as the evaluation metric, 
    and also using stratified K-fold cross-validation.
    
    Parameters:
    - model: xgboost model
    - X: features
    - y: labels
    - n_splits: number of splits for K-fold cross-validation (default: 5)
    
    Returns:
    - mean ROC AUC score from K-fold cross-validation
    """
    predictions = []
    true_values = []
    skf = StratifiedKFold(n_splits=5, random_state=RANDOM_STATE, shuffle=True)
    for train_index, val_index in skf.split(X, y):
        X_train, X_val = X[train_index], X[val_index]
        y_train, y_val = y.iloc[train_index], y.iloc[val_index]
        model.fit(X_train, y_train)
        y_pred = model.predict_proba(X_val)[:, 1]
        predictions.append(y_pred)
        true_values.append(y_val)
    predictions = np.concatenate(predictions)
    true_values = np.concatenate(true_values)
    auc_roc = roc_auc_score(true_values, predictions)
    return predictions, auc_roc

predict_and_score(ensemble_model, X_train_scaled, y_train)
```
``````

## Create blank table in SQL

```
BEGIN;

CREATE TABLE IF NOT EXISTS project
(
    id uuid NOT NULL,
    ngo_id uuid,
    name character varying(255),
    location character varying(255),
    start_date date,
    end_date date,
    nature_of_intervention character varying(255),
    project_sector character varying(255),
    budget numeric,
    external_funding_received numeric,
    no_of_beneficiaries integer,
    type character varying(255),
    photos_link text,
    documents_link text,
    description text,
    status character varying(255),
    manager character varying(255),
    budget_allocation numeric,
    budget_utlization numeric,
    impact character varying(255),
    report_link text,
    CONSTRAINT "Project ID" PRIMARY KEY (id)
);

END;
```

Basic syntax:

```
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);
```

```
INSERT INTO students (id, name, age)
VALUES (1, 'John Doe', 22);
```

Insert multiple rows of data into a table at once

```
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...),
       (value4, value5, value6, ...),
       (value7, value8, value9, ...),
       ...;
```

## TODO

- [ ]  Fork [Codebook Repository](https://github.com/DaanMatch/Codebook), may review the work done by previous DS Discovery participants
- [ ] Create a branch using your name
- [ ] Perform EDA and preliminary data cleaning on datasets
- [ ] Create a data dictionary (we will work towards creating a codebook on the data you will be webscrapings)
- [ ] Create SQL version of your data-files
- [ ] Submit this in a folder with your name by creating a pull request to the Codebook repository
- [ ] Short presentation to non-technical stakeholder next meeting 5 mins max each person
