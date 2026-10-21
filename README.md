🎬 Movie Recommender System: Data Preprocessing

A content-based movie recommendation project built on the TMDB 5000 Movies & Credits dataset. This notebook prepares the data by merging the movie and credit tables and combining each film’s metadata into a single text “tags” feature, ready for vectorization and similarity-based recommendations.

📌 Overview

The goal is to recommend movies similar to one a user likes, based on content rather than user ratings. To do that, each movie is represented by a combined text profile built from its plot, genres, keywords, top cast, and director.

📂 Dataset
movies.csv: 4,803 movies, 20 columns (budget, genres, keywords, overview, popularity, revenue, runtime, and more)
credits.csv: 4,803 rows with movie_id, title, cast, crew
🔧 What the Notebook Does
Loads and explores both CSV files with Pandas
Merges movies and credits on the movie ID
Selects relevant columns: movie_id, title, overview, genres, keywords, cast, crew
Drops missing values, leaving 4,800 clean records
Parses JSON-formatted columns (genres, keywords, cast, crew) into clean Python lists using json.loads
Extracts key features:
Top 3 cast members per movie
Director from the crew list
Tokenizes the overview text into words
Removes spaces within names and terms (e.g., Science Fiction → ScienceFiction, Sam Worthington → SamWorthington) so multi-word entities stay as single tokens
Builds a unified tags column by concatenating overview, genres, keywords, cast, and director

The final output is a compact DataFrame with movie_id, title, and tags.

🛠️ Tech Stack
Python
Pandas
JSON
Jupyter Notebook
🚀 Next Steps
Lowercase text and apply stemming
Vectorize tags (Bag of Words / TF-IDF with scikit-learn)
Compute cosine similarity between movies
Build a recommend(movie) function
Deploy as a web app (e.g., Streamlit)
▶️ How to Run
bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
pip install pandas jupyter
jupyter notebook movies__credit.ipynb

Place movies.csv and credits.csv in the project folder before running.
