Movie Recommendation System with MovieLens Data
===============================================

Overview
--------
This project builds a simple movie recommendation system using the MovieLens ratings dataset.
The workflow is implemented in the Jupyter notebook [moviereco.ipynb](moviereco.ipynb) and
covers:

- Data wrangling and feature engineering
- Exploratory data analysis (EDA)
- A basic item-based collaborative filtering recommendation model

The goal is to explore user rating behavior and generate intuitive recommendations for
movies similar to a selected title (e.g., *Toy Story (1995)*).

Dataset
-------
The project uses the MovieLens data files included in this folder:

- [movies.csv](movies.csv): Movie metadata (movieId, title, genres)
- [ratings.csv](ratings.csv): User ratings (userId, movieId, rating, timestamp)
- [ml-latest-small](ml-latest-small): Additional MovieLens files (links, tags, etc.) that
  are not required for the core notebook but come with the original dataset

Getting Started
---------------

### 1. Prerequisites

You will need:

- Python 3.x
- Jupyter Notebook or JupyterLab

Recommended Python packages:

- `pandas`
- `seaborn`
- `matplotlib`

You can install them with:

```bash
pip install pandas seaborn matplotlib
```

### 2. Running the Notebook

1. Open a terminal in this project directory:
	- `cd "C:\Users\Louis\Downloads\Data Analysis\Movie Reco"`
2. Launch Jupyter:
	- `jupyter notebook` (or `jupyter lab`)
3. Open [moviereco.ipynb](moviereco.ipynb).
4. Run all cells in order (Kernel → Restart & Run All) to reproduce the analysis and
	recommendations.

Project Structure
-----------------

- [moviereco.ipynb](moviereco.ipynb): Main analysis and recommendation notebook
- [movies.csv](movies.csv): Movies metadata
- [ratings.csv](ratings.csv): User ratings
- [ml-latest-small](ml-latest-small): Extra MovieLens data files

Methodology
-----------

1. **Data Wrangling & Engineering**
	- Merge movies and ratings on `movieId`.
	- Compute per-movie average rating (`ave_rating`) and rating count (`rating_count`).
	- Filter to movies with at least 50 ratings to focus on reliably rated titles.

2. **Exploratory Data Analysis (EDA)**
	- Inspect the distribution of rating values and overall user generosity.
	- Explore the relationship between popularity (rating count) and average rating.
	- Identify the most frequently rated genres.

3. **Recommendation System**
	- Build a user–movie rating matrix (users as rows, movie titles as columns).
	- For a target movie (e.g., *Toy Story (1995)*), compute correlations between its
	  rating vector and all other movies.
	- Restrict to movies with sufficient rating counts and rank by correlation to
	  produce recommendations.

Possible Extensions
-------------------

- Incorporate additional features (e.g., genres, year) into the recommendation logic.
- Experiment with user-based collaborative filtering and compare results.
- Try more advanced models (e.g., matrix factorization, implicit feedback methods).
- Build a simple web or CLI interface to serve recommendations interactively.

License
-------
This project is for educational and exploratory purposes. Please refer to the
MovieLens dataset terms of use for any restrictions on data usage.
