# MovieLens Exploratory Analysis

Exploratory Data Analysis (EDA) of the **MovieLens 32M** dataset,
developed as part of the data exploration phase for **AuraCinema ---
Movie Discovery Engine**.

The purpose of this repository is to understand the structure, quality,
and characteristics of the MovieLens data before using it to design and
evaluate a movie recommendation approach.

## Objectives

This EDA investigates:

-   The structure and contents of the MovieLens dataset.
-   Data quality, including missing values, duplicate records, and
    rating values.
-   User activity and the distribution of ratings per user.
-   Movie popularity, measured by the number of ratings received.
-   Rating behaviour, including rating distributions and average movie
    ratings.
-   Genre distribution, rating volume by genre, and average ratings by
    genre.

The analysis is descriptive. Findings should be interpreted in the
context of the MovieLens dataset and should not automatically be
generalised to all movie viewers.

## Dataset

This project uses the **MovieLens 32M** dataset published by GroupLens
Research.

-   **Official dataset page:**
    https://grouplens.org/datasets/movielens/32m/
-   **Main files used:**
    -   `movies.csv` --- movie identifiers, titles, and genres.
    -   `ratings.csv` --- user ratings, movie identifiers, and
        timestamps.
    -   `tags.csv` --- user-generated tags associated with movies.
    -   `links.csv` --- identifiers linking movies to external
        databases.

The `ratings.csv` file contains approximately 32 million ratings, so the
notebook processes it in chunks for analyses that require the full
dataset. Some initial inspections may use a smaller sample to keep
exploratory steps manageable.

### Downloading and storing the data

1.  Download the MovieLens 32M dataset from the official GroupLens page.
2.  Extract the archive locally.
3.  Place the dataset files in the location expected by the notebook, or
    update the notebook's `data_path` variable to match your local
    folder structure.

**Note:** The raw dataset is large. Unless there is a specific reason to
version it in Git, keep the dataset files out of the repository and
follow the dataset's terms of use. The notebook requires the data to be
available locally to run the analysis.

## Repository Structure

The notebook is expected to be stored in a `notebooks/` directory, with
the extracted dataset in `data/ml-32m/` at the repository root:

``` text
MovieLens_exploratory_analysis/
├── data/
│   └── ml-32m/                 # Local dataset files (not committed to Git)
├── notebooks/
│   └── 01_movielens_exploratory_analysis.ipynb
├── .gitignore
└── README.md
```

If your actual folder structure differs, adjust `data_path` in the
notebook accordingly.

## Analysis Workflow

The notebook is organised into sections that progressively explore the
data:

1.  **Introduction** --- introduces the exploratory data analysis and its objectives.
2.  **Dataset Overview** --- initial observation of the dataset and its files.
3.  **Data Quality** --- inspects columns, data types, missing values, duplicates, and rating values.
4.  **User Behaviour** --- examines the number of ratings per user and
    differences in user activity.
5.  **Movie Popularity** --- identifies how many ratings each movie has
    received.
6.  **Rating Behaviour** --- explores rating distributions, average
    movie ratings, and the relationship between rating count and average
    rating.
7.  **Genre Analysis** --- examines the distribution of genres, rating
    volume by genre, and average ratings by genre.
8.  **Temporal Analysis** --- examines how movie rating activity changes over time.
9.  **User-Movie interactions** --- examines the number of recorded user-movie interactions, the distribution of interactions across users and movies, and the sparsity of the user-movie interaction matrix.
10.  **Conclusions** --- summarises the main findings, discusses their implications for the recommendation system and identifies the limitations and next steps.

## Requirements

The notebook uses Python and the following main libraries:

-   [Pandas](https://pandas.pydata.org/) --- data loading, manipulation,
    and aggregation.
-   [NumPy](https://numpy.org/) --- numerical operations.
-   [Plotly](https://plotly.com/python/) --- interactive visualisations.

Jupyter Notebook or JupyterLab is also required to run the notebook
interactively.

## Setup and Usage

The notebook was developed in a Python environment named `AuraCinema`.
You can use a different environment, provided the required dependencies
are installed.

For example, with Conda:

``` bash
conda create -n AuraCinema python=3.11
conda activate AuraCinema
pip install pandas numpy plotly jupyter ipykernel
```

Then:

1.  Open Jupyter Notebook or JupyterLab from the environment.
2.  Open `notebooks/01_movielens_exploratory_analysis.ipynb`.
3.  Confirm that `data_path` points to the extracted MovieLens dataset.
4.  Run the notebook cells in order.

The notebook processes the full ratings file in chunks for several
aggregate analyses. These cells may take some time to finish depending
on your computer.

## Important Notes

-   **Rating count is not movie quality.** A movie with more ratings has
    more recorded interactions in this dataset, but that does not mean
    it is better.
-   **Average ratings require context.** Movies with very few ratings
    can have unusually high or low averages.
-   **Genres overlap.** A movie can belong to multiple genres, so
    genre-level movie and rating counts are not mutually exclusive.
-   **Dataset limitations matter.** The analysis describes MovieLens
    users and their recorded interactions; it does not necessarily
    represent the general population.
-   **No recommendation model is defined by this EDA alone.** The
    findings will help inform later decisions about useful features and
    recommendation approaches for AuraCinema.

## Project Context

This repository focuses on exploratory analysis only. It is a
preparatory stage of **AuraCinema --- Movie Discovery Engine**, a movie
discovery project exploring personalised recommendations and ways to
help users discover films beyond their usual preferences.

## Acknowledgements

The MovieLens dataset is provided by **GroupLens Research** at the
University of Minnesota.

Dataset source: https://grouplens.org/datasets/movielens/32m/
