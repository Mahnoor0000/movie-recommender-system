#  Movie Recommender System

A **content-based movie recommender system** built using the TMDB 5000 Movies and Credits datasets.  
This project combines **data preprocessing, NLP-based feature extraction**, and a **Streamlit web interface** to recommend similar movies based on user input.

---

##  Overview

The goal of this project is to recommend movies by analyzing their **content**, such as genres, keywords, cast, and crew — rather than relying on user ratings or collaborative data.  
The recommender uses **cosine similarity** between vectorized movie features to identify the most similar titles.

---

##  How It Works

1. **Data Merging & Cleaning**  
   - The TMDB 5000 Movies and Credits datasets are merged on the movie title.  
   - Irrelevant columns are dropped, missing values removed, and text columns standardized.

2. **Feature Engineering**  
   - Extract key attributes: `genres`, `keywords`, `cast`, `crew`, and `overview`.  
   - Convert them into list formats and concatenate them into a single `tags` column.

3. **Text Preprocessing**  
   - Apply stemming using `PorterStemmer` to unify similar words.  
   - Remove spaces and punctuation to ensure consistency.

4. **Vectorization & Similarity Matrix**  
   - Use `CountVectorizer` to transform text into numerical vectors.  
   - Compute **cosine similarity** among all movie vectors.

5. **Recommendation Function**  
   - Given a movie title, the function fetches the top N similar movies based on the precomputed similarity matrix.

6. **Web App Interface**  
   - Built with Streamlit (`app.py`) for interactive movie recommendations.  
   - Users can type a movie name and instantly get similar movie suggestions.
