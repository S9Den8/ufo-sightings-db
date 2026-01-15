# UFO Sightings Analysis Project

Project Overview
This project analyzes more than 80,000 global UFO sighting reports. The goal is to explore temporal patterns, geographic distribution, common sighting characteristics, and reporting behavior using structured exploratory data analysis (EDA) and visualization techniques.

The project consists of two notebooks:
- 1. Data cleaning and preprocessing
- 2. Exploratory data analysis and initial visualizations

Both notebooks are fully reproducible using the environment setup described below.

## 1. Data Cleaning, Standardization, and Exploratory Analysis

### Project Overview

This project processes a global UFO sightings dataset from 1906–2014, transforming it into a clean, standardized, and geospatially reliable resource for:
- Exploratory Data Analysis (EDA)
- Geospatial visualization
- Pattern and trend identification
- Machine learning
The repository contains the cleaning pipeline, EDA notebook, and Week 2 visualizations from the Keystone Capstone.

### Dataset

- Source: Kaggle — UFO Sightings (1906–2014)
- Records: ~88,000 global sightings
- Final Cleaned Dataset: ~79,600 valid entries
- Key Fields: datetime, city, state, country, shape, duration, comments, latitude, longitude

### Project Motivation:

UFO reports offer a unique lens into human perception, reporting behavior, geography, and long-term cultural trends. Before conducting any modeling or pattern discovery, the dataset required extensive cleaning and standardization. This project establishes the foundation for later geospatial, temporal, and statistical analysis.


#### Objectives: 

The primary cleaning and preparation steps included:
- Standardizing all geographic fields (city, state, country)
- Validating and cleaning latitude/longitude values
- Converting the dataset into a GeoDataFrame-compatible structure
- Assigning countries and U.S. states via spatial joins
- Normalizing country and state codes into ISO 2-letter format
- Resolving missing, ambiguous, and inconsistent entries
- Producing a final, downstream-ready dataset for EDA and modeling



#### Methods & Processing Steps

A summary of the major operations performed:
- Removed formatting inconsistencies, stray whitespace, invalid symbols, and non-standard text
- Converted coordinate fields to numeric and validated ranges
- Created a geometry column for geospatial processing
- Applied CRS standardization (EPSG:4326)
- Performed spatial joins to infer missing country/state values
- Built mapping dictionaries for country and state normalization
- Applied pycountry for ISO-compliant country codes
- Conducted full validation checks (missing values, coordinate integrity, unique values)
- Trimmed and standardized durations, handling extreme outliers
- Exported the final cleaned dataset as ufo_final_cleaned.csv


#### Final Output: File: ufo_final_cleaned.csv

Contains:
- Cleaned city, state, and country fields
- Validated latitude and longitude
- Standardized shape and duration fields
- Fully geospatial-ready structure
- ~79,600 high-quality, analysis-ready records

## 2. Exploratory Data Analysis 

The EDA notebook addresses temporal trends, geographic distributions, seasonal patterns, state- and city-level frequency, shape comparisons, and duration analysis.
Key Findings (Early Insights)
- Reports increased significantly beginning in the early 1990s.
- The United States accounts for more than 70,000 of the ~80,000 global records.
- July exhibits the highest monthly counts (9,542 sightings).
- The top U.S. states by volume include California (9,603), Washington (4,255), and Florida (4,163).
- The most frequently reported shapes are light, triangle, and circle.
- Duration distributions are highly skewed, with many short sightings and a long heavy tail.

### Repository Structure

/data  
    ufo_final_cleaned.csv  
    ufo_sightings_raw.csv  

/notebooks  
    ufo_eda_&_visuals.ipynb  
    ufo_sightings_initial_exploration.ipynb  

/shapefiles  
    us_states.geojson  
    world.geojson  

README.md  
requirements.txt  

Environment Setup (Reproducible Workflow)

This project uses a local virtual environment (.venv) created with the Python interpreter provided by a Conda installation. This allows reproducibility while keeping dependencies contained inside the project.

Select the Conda Python Interpreter
Install Miniconda or Anaconda.
Ensure Conda provides the interpreter by running:
python --version

In VS Code, select the interpreter named:
conda: ufo (Python 3.11)

Create the Project Virtual Environment
Inside the project folder, create a virtual environment using Conda’s Python:
python -m venv .venv

Activate the virtual environment:

Windows PowerShell:
..venv\Scripts\activate

macOS / Linux:
source .venv/bin/activate

Install Dependencies
Once the .venv is active, install all required packages:
pip install -r requirements.txt

Launch Jupyter Notebook
With the environment activated:
jupyter notebook

Open the notebook located at:
notebooks/ufo_eda_and_visuals.ipynb

### Dataset Source

Kaggle: UFO Sightings (1906–2014)
The cleaned dataset provided here is derived from the original and processed for research purposes only.

### Requirements

- Python 3.10+

The following libraries must be included in the requirements.txt file because they were used throughout the project:
- pandas
- numpy
- matplotlib
- seaborn
- plotly
- geopandas
- shapely
- pyproj
- rtree
- fiona
- pycountry
- requests
- urllib3

These packages support data cleaning, statistical summaries, visualization, and geospatial mapping.

### Dataset Limitations

The dataset consists of publicly submitted UFO sighting reports. As such, the following limitations should be considered when interpreting results:

- Geographic representation varies significantly, with the United States contributing the majority of reports.
- Reporting frequency may reflect population density, internet access, or cultural factors rather than actual sighting frequency.
- Older entries contain inconsistent formatting, missing values, or limited contextual detail.
- Some coordinate and duration values required correction or filtering during preprocessing.
- Observed trends may reflect reporting behavior rather than changes in UFO activity.

### Reproducibility Notes

- All preprocessing steps are documented in the data cleaning notebook and can be reproduced by running each cell in order.
- No proprietary tools or external APIs are required.
- All visualization and analysis can be reproduced entirely within the .venv environment.

## Status
Initial data exploration and full EDA are complete.
