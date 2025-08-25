📚 Book Recommendation System Using K-Nearest Neighbors

This project implements a book recommendation system using the K-Nearest Neighbors (KNN) algorithm. The system recommends books similar to a given book based on user ratings.

The dataset used is the Book-Crossings dataset, which contains:

Over 1.1 million ratings on a scale of 1–10

270,000 books

90,000 users

Project Overview

The main goal is to suggest books that are most similar to a target book based on user preferences. We achieve this using the KNN algorithm, which calculates distances between books in the rating space.

To ensure meaningful recommendations, we filter the data to include:

Users with at least 200 ratings

Books with at least 100 ratings

This removes sparsely rated books and inactive users, improving recommendation quality.

Features

Filter dataset for statistically significant ratings

KNN-based similarity search

Interactive recommendation function: get_recommends(book_title)

Returns a list of 5 recommended books with distances

Installation

Clone the repository:

git clone https://github.com/yourusername/book-recommender.git
cd book-recommender


Install required Python packages:

pip install -r requirements.txt


Dependencies include: pandas, numpy, scikit-learn

Download the Book-Crossings dataset and place the CSV in the project directory.

Usage
from recommender import get_recommends

# Example usage
recommendations = get_recommends("The Queen of the Damned (Vampire Chronicles (Paperback))")
print(recommendations)


Example Output:

[
    'The Queen of the Damned (Vampire Chronicles (Paperback))',
    [
        ['Catch 22', 0.793983519077301],
        ['The Witching Hour (Lives of the Mayfair Witches)', 0.7448656558990479],
        ['Interview with the Vampire', 0.7345068454742432],
        ['The Tale of the Body Thief (Vampire Chronicles (Paperback))', 0.5376338362693787],
        ['The Vampire Lestat (Vampire Chronicles, Book II)', 0.5178412199020386]
    ]
]


The first element is the input book.

The second element is a list of recommended books and their similarity distances.

How It Works

Data Cleaning: Remove inactive users and rarely rated books.

Create Book-User Matrix: Rows = books, Columns = users, Values = ratings.

Train KNN Model: Using sklearn.neighbors.NearestNeighbors.

Get Recommendations:

For a given book, find nearest neighbors in rating space.

Return top 5 similar books with distances.


Push to branch (git push origin feature-name)

Open a Pull Request
