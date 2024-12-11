Python Project - London Housing Dataset

This project explores the housing market trends in London, UK, over a 24-year period (1995–2019). The dataset includes crucial information such as:

    Monthly average house prices
    Yearly number of houses sold
    Monthly number of crimes committed

The analysis builds upon a YouTube project and dataset from Kaggle, with added insights and in-depth exploration.

YouTube Reference:
London Housing Dataset Analysis
Dataset Overview

The dataset contains 13,549 rows and 6 columns with the following fields:

    date: Date of record
    area: London borough or area name
    average_price: Average house price in GBP
    code: Area code
    houses_sold: Number of houses sold
    no_of_crimes: Number of crimes reported

Example Records:
date	area	average_price	code	houses_sold	no_of_crimes
1995-01-01	city of london	91449	E09000001	17.0	NaN
1995-02-01	city of london	82203	E09000001	7.0	NaN
Key Objectives

This project seeks to answer important questions about the London housing market:

    How clean is the dataset?
        Missing value analysis for columns like no_of_crimes and houses_sold.
    What are the trends and patterns in housing prices and crime rates over the years?
    What are the maximum and minimum average_price per year in England?
    What are the trends in crime rates across various boroughs?
    Which areas have average prices below £100,000, and how do they compare?

Techniques and Analysis

    Data Cleaning:

        Analyzed missing values:

Housing_Data.isnull().sum()

    Observed significant missing values in no_of_crimes.

Visualized missing values using heatmaps:

    import seaborn as sns
    sns.heatmap(Housing_Data.isnull())

Data Transformation:

    Converted date to datetime format:

    Housing_Data['date'] = pd.to_datetime(Housing_Data['date'])

    Extracted year and month into separate columns for analysis.

Insights & Aggregations:

    Grouped data by year and calculated:
        Maximum, minimum, and average house prices:

Housing_Data.groupby('year').average_price.max()

Crime rate trends:

        Housing_Data.groupby('area').no_of_crimes.min()

Filtering Data:

    Identified boroughs with average house prices below £100,000:

        Housing_Data[Housing_Data.average_price < 100000].area.value_counts()

Results

    Significant missing values in the no_of_crimes column post-2000.
    City of London exhibited unique characteristics, with consistently low housing sales and crime records.
    Maximum housing price trends showed a steady increase, peaking in 2019.
