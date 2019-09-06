# Book-Recommendation-System

Project Description: Book Recommendation System

Type: Collaborative based recommendation (Recommend on the basis of what previous users rated(Item-Item collaborative recommender system)

How it works: Enter a book name and it prints the top 5 books which have similar rating of the book entered by the user.

The dataset have 2 CSV files. In first csv file, fields are ISBN, book title, Book author and Publication House. In second csv file, fields are ISBN, user ID, User rating, user country.

Prepare a data frame which is a result of merging of these two csv files on the basis of ISBN no. as ISBN behaves as primary key. After merging the csv files, drop those columns which are of no use and these are book author, publication house and user country. To get the best possible recommendation, checking for the outliers as all the ratings are between 0-5. So after plotting the ratings with y=0 and get some ratings are below than 0 and some are above 5. The maximum rating was 9, so what I assumed was that the user might confused of the scale of rating, he took out of 10 scale. So just half those values which are greater than 5 and make the ratings less than 0 equals to 0. Now after dealing with the outliers, next work is to ensure the unbiased recommendation. So achieve this, we add a column to the data frame which contains the count of no. of users rated a particular book. Now make a new data frame which contains those books ratings only which has count of users more than 50. After achieving the unbiased nature, next work is to make the data frame compatible for applying algorithm. Now converting the data frame into a pivot table which has index as book title, columns as user ID and values as user ratings. Now making a sparse matrix from this pivot table which automatically converts all ratings for a particular to its sum average. Now Data frame is ready to apply algorithm. Using KNN with the use cosine distance between ratings was applied and thus our recommendation system is ready.

