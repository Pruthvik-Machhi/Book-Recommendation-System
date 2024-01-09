# Book-Recommendation-System

Book recommendation using collaberative filtering

1. Introduction :
This project is to help we discover new books we&#39;ll love. We&#39;ve built a smart system that
suggests books based on what we&#39;ve enjoyed before. By analyzing how people rate
and read books, our system finds patterns to recommend similar ones.
we can tell us about a book we liked, and we&#39;ll suggest others that we might enjoy.
Our system uses clever tricks to match books we might not have discovered on wer
own. We&#39;ve sorted through lots of data about books and how people like them to
make our suggestions as accurate as possible.the project is all about making it easier for we to find wer next favorite book.
Whether it&#39;s mystery, romance, or sci-fi, we&#39;re here to help we explore new
adventures in the world of books!

we are using Collaborative Filtering in our project

- Collaborative filtering analyzes user behavior, preferences, and interactions with books. It identifies patterns among users who liked similar books and recommends other books liked by those users. 
There are two types:
     - User-based Collaborative Filtering: Recommends books to a user based     on the preferences of similar users.
     - Item-based Collaborative Filtering: Recommends books similar to the ones a user has liked before.

2.Data set:
Three separate files(csv):
Books: 
- Contains basic information regarding the books.(270k+ books)
ISBN, Title, Author, Year of publication, Publisher
Ratings: 
- Contains all of the user rating information.(1 million+  ratings)
UserID, ISBN, Rating(1-10) 10 being the highest
Users: 
- Contains basic information regarding the reader.(275k+ users)
UserID, Location, Age

3.Implementation:

Here is an improved explanation, integrating the details about the brute-force algorithm and cosine similarity:


Data Loading and Filtering:
 - The code begins by importing book details, user information, and ratings from CSV files.
    - Merges the ratings with book details and filters users who have rated more than 50 books and books rated at least 10 times.
    - Generates a pivot table to organize ratings by book titles and user IDs.

 Nearest Neighbors Model Initialization (Brute Algorithm and Cosine Similarity):
 - Converts the pivot table into a sparse utility matrix using `csr_matrix` from SciPy.
    - Initializes a `NearestNeighbors` model using the brute-force algorithm (`algorithm='brute'`), comparing all pairs of points for nearest neighbor computation, suitable for smaller datasets.
    - Employs cosine similarity (`metric='cosine'`) to measure the cosine of the angle between vectors, facilitating similarity calculations among different items in the utility matrix.


 Recommendation Function:
    - Defines a `recommend` function that accepts a book name as input and employs the K-Nearest Neighbors (KNN) algorithm with cosine similarity to suggest similar book recommendations.
    - Attempts to find recommendations for the input book and offers similar book suggestions if the input book is not present in the dataset.
 

User Interaction Loop:
- Executes a continuous loop that enables users to input book names within a console-based interface until they input 'exit'.
    - Utilizes the `recommend` function for each user-entered book name, providing book recommendations or exiting the recommendation system based on user inputs.

This code overview illustrates the sequence of actions, including data loading, model initialization using a brute-force algorithm and cosine similarity, defining recommendation functionality, and enabling user interaction within a console-based interface for suggesting similar book recommendations.

4.Result :

*********************************************
Enter the Book Name (Type 'exit' to stop):  Houses of Stone
Recommendations for 'Houses of Stone':
1: Greygallows
2: Mrs. Pollifax Pursued (Mrs. Pollifax Mysteries (Paperback))
3: Night Train to Memphis
4: Selected Poems (Dover Thrift Edition)
5: Snake, the Crocodile &amp; the Dog, The (Amelia Peabody Mysteries (Paperback))
*********************************************
Enter the Book Name (Type 'exit' to stop):  exit
Exiting the recommendation system.

5.Conclusion :

This project is centered on revolutionizing book recommendations through a sophisticated collaborative filtering system. Leveraging the K-Nearest Neighbors (KNN) algorithm with brute-force computation, our system offers personalized book suggestions based on user preferences. Focusing on enhancing user interaction, the system efficiently recommends the top 5 books aligned with individual tastes. Moreover, it adeptly handles challenges such as spelling errors and incomplete book titles, ensuring accurate and relevant recommendations.




