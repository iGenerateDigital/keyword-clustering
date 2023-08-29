# 3D Keyword Clustering for SEO

## Overview

The 3D Keyword Clustering script is designed to help SEO specialists, data analysts, and digital marketers optimize their keyword targeting strategies. By using machine learning algorithms and natural language processing techniques, this script clusters keywords in a 3D space based on their relevance to specific web pages and search queries.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [How It Works](#how-it-works)
- [Contributing](#contributing)
- [License](#license)

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/3D-Keyword-Clustering.git

## Usage

To run the script, navigate to the directory where main.py is located and execute:

python main.py

## How It Works

### TF-IDF Vectorization
The script uses Term Frequency-Inverse Document Frequency (TF-IDF) to convert each keyword into a numerical vector. This quantifies the 'importance' of each keyword in relation to the corpus.

def fit_vectorizer(corpus):
    stop_words = set(stopwords.words('english'))
    return TfidfVectorizer(stop_words=list(stop_words), ngram_range=(1, 2)).fit(corpus)

### Cosine Similarity
Cosine similarity is calculated between the TF-IDF vectors of the keyword and the unique web pages/search queries.

def calculate_similarity(vectorizer, phrase1, phrase2):
    vectors = vectorizer.transform([phrase1, phrase2]).toarray()
    return cosine_similarity(vectors)[0, 1]

### Keyword Scoring
Each keyword is given a similarity score based on its relevance to specific web pages and primary topics.

def compute_keyword_similarity_scores(keyword, topics, pages, vectorizer):
    topic_scores = {topic: calculate_similarity(vectorizer, keyword, topic) for topic in topics}
    ...

### Benefits

This approach offers a nuanced way to cluster keywords for SEO. By thinking of a website as a 3D object rather than a 2D plane, we can better understand the relationships between keywords, web pages, and user queries. This could significantly enhance SEO strategies, making them more dynamic and tailored to various dimensions of user engagement and content relevance.

## Contributing

If you would like to contribute, please read CONTRIBUTING.md for details on the code of conduct and the process for submitting pull requests.

## License
This project is licensed under the MIT License. See the LICENSE.md file for details.
