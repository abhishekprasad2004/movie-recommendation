# movie-recommendation
content based

dataset link :- https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata
ast.literal_eval

    Used for: Converting string representations of lists (e.g., genres, cast, keywords) into actual Python list objects.

    Why: Dataset columns like genres or cast may be stored as strings, not lists; to extract and manipulate these properly, conversion is needed.

    Function: Ensures data from the dataset can be accessed and processed as Python objects rather than plain strings.

Concatenated important attributes into a new column tags

    Used for: Combining key features like overview, genres, keywords, cast, and crew into one column.

    Why: To have a unified text column that captures the essence of the movie for content-based filtering.

    Function: Creates a simplified and meaningful input for the model to process movie features effectively.

Converted tags column into string using join() function

    Used for: Merging all list elements in tags into a single string of space-separated words.

    Why: Machine learning models like CountVectorizer require plain text input.

    Function: Transforms feature lists into a suitable text format for vectorization.

Applied stemming

    Used for: Reducing words to their root forms (e.g., “loved”, “loving” → “love”).

    Why: Helps the model treat similar words with the same meaning as one, reducing redundancy.

    Function: Improves matching of related terms and boosts accuracy in similarity calculations.

Created vectors using CountVectorizer

    Used for: Converting the text data in the tags column into a matrix of token counts (Bag-of-Words model).

    Why: To numerically represent text data so that mathematical similarity calculations can be performed.

    Function: Produces feature vectors for each movie based on the frequency of words.

**Calculated similarity using cosine similarity

    Used for: Measuring the similarity between two movie vectors based on the angle between them.

    Why: Cosine similarity is effective for high-dimensional sparse data like text.

    Function: Determines how similar two movies are based on their content.

Used enumerate() to fix the index for similarity scores

    Used for: Pairing similarity scores with their respective movie indices.

    Why: Required to maintain the connection between similarity value and corresponding movie.

    Function: Helps identify and sort the top 5 most similar movies by keeping track of indices.
