# 1. UFO Sightings - Initial Exploration

## Project Overview
This project explores a dataset of UFO sightings reported between 1906-2014. The goal is to produce a reliable, analysis-ready dataset for exploratory data analysis, geospatial modeling, and future machine leaning applications.

## Dataset
- Source: Kaggle - UFO Sightings (1906-2014)
- Records: ~88,000+ global sightings
- Fields processed: datetime, city, state, country, shape, duration, latitude, longitude

### Objectives: 
- Standardize all geographic fields (city, state, country).
- Validate and clean latitude/longitude values.
- Convert the dataset into a GeoDataFrame.
- Align shapefiles to EPSG:4326 for accurate spatial operations.
- Assign countries and U.S. states using spatial joins.
- Normalize country and state names into ISO 2-letter codes.
- Resolve missing, ambiguous, and incorrect geographic entries.
- Produce a final, fully cleaned dataset for downstream analysis.

### Methods & Processing Steps
- Removed formatting inconsistencies, whitespace, invalid symbols, and non-standard text.
- Converted coordinate fields to numeric and checked for missing/invalid values.
- Created a geometry column for geospatial processing.
- Applied CRS standardization (EPSG:4326) across world and U.S. boundary shapefiles.
- Performed spatial joins to assign countries and U.S. states from polygon boundaries.
- Built mapping dictionaries for state and country code normalization.
- Applied pycountry for ISO-standard 2-letter codes; corrected edge cases manually.
- Conducted full validation checks (missing values, unique values, coordinate integrity).
- Sorted final dataset chronologically and exported to CSV.

### Final Output: File: ufo_final_cleaned.csv
- Contains:
- Cleaned city and shape fields
- Validated latitude & longitude
- Standardized state & country (ISO-2 codes)
- Cleaned durations and comments
- Fully geospatial-ready structure

### Requirements
- Python 3.10+
- pandas, numpy, geopandas, shapely, pycountry


## Status
Initial data exploration is complete for now