# Movie Recommendation System

A content-based movie recommender. Given a movie title, it suggests similar movies based on genre, keywords, tagline, cast, and director.

## How it works

1. **Feature combination** — merges `genres`, `keywords`, `tagline`, `cast`, and `director` into a single text feature per movie.
2. **Vectorization** — converts the combined text into TF-IDF vectors.
3. **Similarity scoring** — computes cosine similarity between all movie vectors.
4. **Fuzzy matching** — uses `difflib` to match a user's typed movie title to the closest title in the dataset, so the input doesn't need to be exact.
5. **Recommendation** — returns the top matches ranked by similarity score.

## Tech stack

- Python
- pandas, NumPy
- scikit-learn (`TfidfVectorizer`, `cosine_similarity`)
- difflib (fuzzy title matching)

## Contents

```
Movie-Recommendation-System/
├─ movies.ipynb   # feature engineering, vectorization, and recommendation logic
├─ LICENSE
└─ README.md
```

## How to run

1. Get a movies dataset with `genres`, `keywords`, `tagline`, `cast`, and `director` columns (e.g. the [TMDB 5000 Movies dataset](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)).
2. Install dependencies: `pip install pandas numpy scikit-learn`
3. Run `movies.ipynb` top to bottom.
4. When prompted, enter your favorite movie name — the notebook prints the closest recommendations.

## Notes

The notebook currently reads `movies.csv` from a Google Colab path (`/content/movies.csv`). Update this path if running locally.
