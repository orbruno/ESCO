
# ESCO Occupations and Skills Analysis

This project is focused on analyzing the ESCO (European Skills, Competences, Qualifications, and Occupations) database to identify specific skills related to certain keywords. The analysis is performed using a Jupyter notebook, which processes data from ESCO CSV files to extract relevant information.

## Project Overview

The main goal of this project is to search for specific keywords within the ESCO datasets to find related skills. This can be particularly useful for job seekers, employers, and researchers who are interested in understanding the skills associated with various occupations.

## ESCO Occupations

### ESCO Occupations Dataset

The ESCO occupations dataset includes standardized descriptions of occupations, their tasks, skills, competences, and other relevant information. It provides structured data about various job roles and their attributes, facilitating matching between job seekers and job vacancies.

### ESCO Occupation Collection

This refers to a specific subset or collection of occupations within ESCO that are being studied or researched in more detail. It may include occupations under review for updates, new occupations being proposed for inclusion, or those being analyzed for their impact or relevance within a particular context or study.

## ESCO Skills

### ESCO Skills Associated with Data Science

The notebook identifies ESCO skills associated with data science by searching for specific keywords in the occupations dataset. This includes roles such as data engineer, data scientist, artificial intelligence engineer, database integrator, data quality specialist, and data analyst.

## Requirements

- Python 3.x
- pandas
- Jupyter Notebook

## Setup

1. Clone the repository:
    ```sh
    git clone <repository-url>
    ```

2. Install the required Python packages:
    ```sh
    pip install pandas jupyter
    ```

3. Download the ESCO files (CSV format) and place them in the project directory.

## Usage

1. Open the Jupyter notebook:
    ```sh
    jupyter notebook Database Analysis.ipynb
    ```

2. Run the notebook cells to load the datasets and perform the analysis.

## Notebook Structure

### Loading ESCO Occupations Data

The notebook starts by loading the ESCO occupations CSV file into a DataFrame:
```python
import pandas as pd

# Load the occupations CSV file into a DataFrame
occupations_df = pd.read_csv('occupations_en.csv')
```

### Searching for Data-Related Occupations

It then filters the DataFrame to find occupations related to data science by searching for specific keywords:
```python
data_science_occupations_df = occupations_df.loc[
    occupations_df['preferredLabel'].str.contains(
        'data engineer|data scientist|artificial intelligence engineer|database integrator|data quality specialist|data analyst', 
        case=False, 
        na=False
    )
]
```

### Loading and Analyzing Occupation Collection

The notebook also processes a specific collection of occupations for detailed study:
```python
# Load the occupations collection CSV file into a DataFrame
occupations_collection_df = pd.read_csv('researchOccupationsCollection_en.csv')

# Filter data-related occupations
data_occupations_collection_df = occupations_collection_df.loc[
    occupations_collection_df['preferredLabel'].str.contains('data', case=False, na=False)
]
```

## Output

The results include a list of occupations and their associated skills that match the specified keywords. This information can be used for various purposes, including career planning, job matching, and educational program development.

## Contributing

Contributions are welcome! Please fork the repository and submit pull requests.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

---

This README provides an overview of the project's purpose, setup instructions, and usage guidelines, ensuring that users can easily understand and utilize the notebook for analyzing ESCO data.
