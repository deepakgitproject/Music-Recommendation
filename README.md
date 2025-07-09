# Music Recommendation System 🎵

This project is a content-based music recommendation system that suggests songs based on lyrical similarity. It uses a Python backend for model creation and a Streamlit frontend for an interactive user experience. Album art is fetched using the Spotify API to create a visually appealing interface.

---

## 📜 Project Overview

The core of this project is to recommend songs by analyzing their lyrics. The process involves:
1.  **Preprocessing** song lyrics from a dataset.
2.  **Vectorizing** the cleaned lyrics using TF-IDF.
3.  **Calculating** the cosine similarity between all songs to find the most similar ones.
4.  **Building** an interactive web app where users can select a song and get the top 5 recommendations.

---

## ✨ Features

-   **Lyrical Similarity**: Recommends songs with similar lyrical content.
-   **Interactive UI**: A user-friendly interface built with Streamlit allows users to select a song from a dropdown menu.
-   **Dynamic Album Art**: Fetches and displays album covers for recommended songs using the Spotify API.
-   **Efficient Backend**: The similarity matrix is pre-computed and saved, ensuring quick recommendations.

---

## 💻 Technologies Used

-   **Python Libraries**: `pandas`, `nltk`, `scikit-learn`, `streamlit`, `spotipy`, `pickle`
-   **NLP Techniques**: Text Cleaning, Tokenization, and Stemming (PorterStemmer).
-   **Recommendation Logic**: Term Frequency-Inverse Document Frequency (TF-IDF) & Cosine Similarity.
-   **Web Interface**: Streamlit
-   **External API**: Spotify API

---

## 📂 Project Structure

### 1. Jupyter Notebook - Backend
The backend logic is developed in a Jupyter Notebook (`model_training.ipynb`) and involves the following steps:
-   **Data Loading**: Reading a CSV of songs and sampling 15,000 rows for efficient processing.
-   **Text Preprocessing**: Cleaning the lyrics by converting text to lowercase, removing special characters, and applying stemming.
-   **Vectorization**: Using `TfidfVectorizer` from scikit-learn to convert the processed lyrics into a matrix of TF-IDF features.
-   **Similarity Calculation**: Computing the cosine similarity matrix between all song vectors.
-   **Serialization**: Saving the final DataFrame and the similarity matrix into `pickle` files (`df.pkl` and `similarity.pkl`) for use in the web app.

### 2. Streamlit Web App - Frontend
The frontend (`app.py`) provides the user interface for the recommendation system:
-   **Data Loading**: Loads the pre-processed data and similarity matrix from the `pickle` files.
-   **Spotify Integration**: Authenticates with the Spotify API using `Spotipy` to fetch album art.
-   **User Interface**:
    -   A dropdown menu to select a song.
    -   A "Recommend" button to trigger the recommendation logic.
    -   Displays the top 5 recommended songs in a clean 5-column layout with their names and album covers.

---

## 🤔 Key Concepts for Discussion (Interview Prep)

Be prepared to discuss the following topics:

-   **Why TF-IDF over Word2Vec/BERT?**: TF-IDF is computationally efficient and works well for keyword-based similarity, making it a great baseline. While models like BERT understand semantics better, they require significantly more computational resources.
-   **Why Cosine Similarity?**: It is effective for measuring similarity between documents represented as TF-IDF vectors, as it is independent of document length.
-   **Role of Stemming**: Stemming reduces words to their root form (e.g., "running" -> "run"), which helps in grouping similar words and reducing the dimensionality of the data.
-   **Scalability**: How would you handle millions of real-time users? (e.g., using a more efficient database, pre-calculating recommendations, using a distributed computing framework like Spark).
-   **Collaborative Filtering**: How would you switch to a collaborative filtering approach? (e.g., using user-item interaction data to find users with similar tastes).
-   **Hybrid Systems**: How could you improve the system using Spotify's audio features (e.g., `tempo`, `energy`, `danceability`)? (e.g., by combining content-based recommendations with audio feature similarity).

---

## 🚀 Future Improvements

-   **Advanced Embeddings**: Use `BERT` or other transformer-based models for a deeper semantic understanding of lyrics.
-   **Hybrid Recommender**: Combine the current content-based approach with collaborative filtering or Spotify's audio features for more personalized recommendations.
-   **Feature Enhancement**: Add genre filtering or the ability to generate playlists.
-   **Deployment**: Deploy the application to a cloud service like Streamlit Cloud, Heroku, or AWS for public access.
