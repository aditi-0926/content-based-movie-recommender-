# Content-Based Movie Recommendation System

An end-to-end Python NLP application that analyzes movie metadata (genres, keywords, taglines, cast, and directors) to dynamically recommend the top 30 most relevant films based on a user's movie preference.

## Features

- Recommends movies from a single title
- Tolerates misspelled movie names through fuzzy title matching
- Uses genres, keywords, tagline, cast and director together
- Runs in Google Colab or on a local machine

## Tech stack

- Python 3
- NumPy
- pandas
- scikit-learn (`TfidfVectorizer`, `cosine_similarity`)
- difflib (standard library)

## Dataset

The script expects a file named `movies.csv` with at least these columns:

| Column | Used for |
|---|---|
| `title` | Matching the user's input and printing results |
| `genres` | Feature |
| `keywords` | Feature |
| `tagline` | Feature |
| `cast` | Feature |
| `director` | Feature |

Place `movies.csv` where the script can find it (see the path note under Usage).

##  How It Works
1. **Metadata Fusion**: Combines text fields (`genres`, `keywords`, `tagline`, `cast`, and `director`) into a single text profile for each film.
2. **TF-IDF Vectorization**: Uses `TfidfVectorizer` from `scikit-learn` to convert raw text tokens into a numerical feature matrix.
3. **Cosine Similarity**: Calculates angular similarity scores (`cosine_similarity`) across all vectors to find contextual relationships between movies.
4. **Fuzzy Query Matching**: Utilizes Python's native `difflib` library to catch typos or partial titles entered by the user, automatically mapping inputs to the closest valid movie title in the database.

##  Prerequisites & Installation
Make sure you have Python installed, then install the necessary dependencies via your terminal:

```bash
pip install numpy pandas scikit-learn
```

##  Usage
1. Place your metadata dataset (`movies.csv`) into the same directory as the script.
2. Run the program:
   ```bash
   python movie_recommendation.py
   ```
3. Enter your favourite movie when prompted (e.g., `Iron Man` or even misspelled like `Ironman`). The system will output a ranked list of 30 tailored recommendations.


