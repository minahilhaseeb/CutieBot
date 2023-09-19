# CutieBot - A Movie Recommendation Chatbot

CutieBot is an interactive chatbot designed to understand user sentiments about movies and provide movie recommendations based on user feedback. The chatbot processes user input, extracts movie titles, analyzes sentiments, and leverages collaborative filtering to recommend movies.

## Table of Contents
- [Features](#features)
- [Technical Overview](#technical-overview)
  - [Initialization and Binarization of Ratings](#initialization-and-binarization-of-ratings)
  - [Processing User Input](#processing-user-input)
  - [Title Extraction](#title-extraction)
  - [Sentiment Analysis](#sentiment-analysis)
  - [Handling Ambiguities](#handling-ambiguities)
  - [Movie Recommendations](#movie-recommendations)
  - [Creative Mode Enhancements](#creative-mode-enhancements)


## Features
- Interactive chat interface
- Movie title extraction from user input
- Sentiment analysis of user reviews
- Movie recommendation using collaborative filtering
- Creative mode for enhanced user interactions

## Technical Overview

### Initialization and Binarization of Ratings
- **Algorithm/Technique**: Threshold-based binarization
- **Description**: All ratings above a certain threshold (e.g., 2.5) are classified as '1' (like) and those below as '0' (dislike). This simplifies the recommendation algorithm by working in a binary space.

### Processing User Input
- **Algorithm/Technique**: String parsing and conditional checks
- **Description**: Input strings are parsed to detect keywords or patterns. Various conditional checks determine the user input's context.

### Title Extraction
- **Algorithm/Technique**: Regular expressions and pattern matching
- **Description**: Regular expressions are employed to identify movie titles enclosed in quotes. In creative mode, a more flexible approach is taken to detect titles outside of quotes.

### Sentiment Analysis
- **Algorithm/Technique**: Dictionary-based sentiment analysis and stemming (using PorterStemmer)
- **Description**: Words from the user's input are stemmed and matched against a sentiment dictionary for sentiment scores. The aggregated score determines the input's overall sentiment.

### Handling Ambiguities
- **Algorithm/Technique**: Levenshtein distance (or similar string similarity measure)
- **Description**: In cases of ambiguous movie titles, string similarity measures, such as the Levenshtein distance, are used to determine the closeness of an input to potential movie titles in the database.

### Movie Recommendations
- **Algorithm/Technique**: Collaborative Filtering using Cosine Similarity
- **Description**: 
  - User's binary rating vector is compared with binary rating vectors of all movies in the dataset.
  - Cosine similarity between these vectors is computed to determine the similarity of user preferences to the ratings of each movie.
  - Movies are ranked based on their similarity scores, and top recommendations are provided.

### Creative Mode Enhancements
- **Algorithm/Technique**: Fuzzy string matching, enhanced pattern recognition, and sentiment amplification
- **Description**: 
  - Fuzzy string matching recognizes titles with slight misspellings.
  - Enhanced pattern recognition facilitates flexible movie title detection without strict patterns.
  - Sentiment amplification identifies stronger sentiment words, giving them higher weightage in sentiment analysis.
