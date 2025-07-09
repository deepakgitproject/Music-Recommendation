# Music-Recommendation

<p>Music Recommendation System - Project Notes
 1. Project Overview
 This project recommends songs based on lyrical similarity using TF-IDF vectorization and cosine similarity.
 The backend model is developed in a Jupyter notebook, while the frontend is built with Streamlit.
 The Spotify API is used to display album art for the recommended songs.
 2. Technologies Used- Python Libraries: pandas, nltk, scikit-learn, streamlit, spotipy, pickle- NLP: Stemming (PorterStemmer), Tokenization, Text Cleaning- Recommendation Logic: TF-IDF + Cosine Similarity (Content-Based)- Web Interface: Streamlit (with dropdown & columns)- External API: Spotify API (album art fetching)
 3. Jupyter Notebook - Backend (Data Preprocessing + Model)- Read CSV with pandas and sample 15,000 rows for performance.- Drop unnecessary columns like 'link' and reset index.- Clean text: lowercase, remove newlines and unwanted characters.- Tokenize and apply stemming to reduce words to root forms.- Use TF-IDF Vectorizer to convert lyrics into numerical vectors.- Calculate cosine similarity between songs.- Create a recommendation function to return top 20 similar songs.- Save the dataframe and similarity matrix using pickle for deployment.
 4. Streamlit Web App - Frontend- Load saved 'df.pkl' and 'similarity.pkl' files.- Use Spotipy to authenticate and fetch album covers using Spotify API.- Use Streamlit to display the UI:
  - Dropdown to select song
  - Button to trigger recommendation
  - 5 columns to display song names + album covers- Logic: Recommend top 5 similar songs (based on cosine similarity).
 5. Interview Readiness
 Be prepared to answer:- Why use TF-IDF and not Word2Vec/BERT?- Why cosine similarity?- How does stemming help?- How would you scale this for real-time users?- How would you switch from content-based to collaborative filtering?- How could Spotify's audio features improve the system?
Music Recommendation System - Project Notes
 6. Possible Improvements- Use BERT embeddings for semantic understanding.- Add genre filtering or playlist generation.- Combine content + collaborative filtering (hybrid system).- Deploy the app to Streamlit Cloud, Heroku, or AWS.- Use Spotify audio features (tempo, energy, etc.) for better personalization.</p>
