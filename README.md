# Netflix-Movie-Recommendation-System

## Introduction
This project involved developing a movie recommendation system for Netflix using the Apriori algorithm to analyze customer viewing patterns and identify frequent itemsets. The dataset contained the list of movies that a user watched or likely to watch, with 7466 columns of data.

The objective of the project was to improve the overall user experience on Netflix by recommending movies that the user might be interested in, based on their viewing history. By using the Apriori algorithm, the system was able to identify associations between movies and recommend them accordingly.

## Dependencies 
The following dependencies are required for running the code:

    numpy
    matplotlib
    pandas
    apyori
    
## Data Preprocessing
  The data is read from a CSV file using pandas, and converted into a list of transactions, where each transaction is a list of movies that a user watched or likely to watch.
  
## Generating Association Rules
The apyori library is used to generate association rules based on the list of transactions. The minimum support, confidence, and lift thresholds are set to 0.003, 0.2, and 3, respectively. The generated rules are stored in a list for further analysis.

## Analyzing Results
The results are analyzed by extracting the movie pairs with the highest support, and the top 10 pairs are displayed in a pandas DataFrame.

    movie_1         = [tuple(result[2][0][0])[0] for result in results]
    movie_2         = [tuple(result[2][0][1])[0] for result in results]
    supports    = [result[1] for result in results]
    return list(zip(movie_1, movie_2, supports))
    resultsinDataFrame = pd.DataFrame(inspect(results), columns = ['Movie 1', 'Movie 2', 'Support'])
    resultsinDataFrame.nlargest(n = 10, columns = 'Support')


## Conclusion
This project demonstrates the use of the Apriori algorithm to develop a movie recommendation system for Netflix. The generated association rules can help in identifying movies that users are likely to watch, based on their viewing patterns.
