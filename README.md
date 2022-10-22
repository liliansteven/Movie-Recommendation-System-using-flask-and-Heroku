# Build a Movie Recommendation API using Scikit-Learn, Flask and Heroku

![alt text](https://cdn.vox-cdn.com/thumbor/WhBtiSXd3B_c9zlrjW08KU-7_OU=/0x0:2300x1499/1200x800/filters:focal(966x566:1334x934)/cdn.vox-cdn.com/uploads/chorus_image/image/57988089/Movies_end_of_year_2017.0.jpg)

## But wait, what is a recommendation system ?
Content-Based recommendation works on the principle that if a user likes a certain item then we recommend the user a similar item based on the item’s features or attributes. So in our case, if a user likes a movie of a particular genre or an actor then we recommend a movie on similar lines to our user. So, if a user has watched the movie Joker then our recommendation system would predict movies similar to Joker or with the same cast as that of Joker if we consider the movie’s cast.

<hr>

# Source Datasets:- 
- TMDB 5000 Movies Dataset: https://www.kaggle.com/tmdb/tmdb-movie-metadata
- The Indian Movie Database: https://www.kaggle.com/tmdb/tmdb-movie-metadata
## Dataset Overview
### we have 6477 movies in our dataset with the following attributes:-

cast: Top 3 actors/actresses of the movies
genres: Top 3 genres of the movies
movie_id: TMDb and IMDb IDs for Hollywood and Bollywood movies
original_title: Title of the movies
plot: Basic overview of the movie

<hr>

# cleaning folder Description:-
## cleaningData.ipynb 
- cleaning/preprocessing the data set before getting into a recommendation

<hr>

# recommendation folder Description:- 
## recommendation.py
Here, we have our logic written for the recommendation algorithm. Consists a total of 5 functions

### get_data():-
- get_data() is used to fetch the data about the movies and return the dataset with it's attributes as the result for further preprocessing.

### combine_data():-
- combine_data() drops the columns not required for feature extraction and then combines the cast and genres column,finally returning the combine column as the result of this function.

### **It will be helpful for you to have a basic understanding of these topics before we move on to the next part :- **
- [Sparse Matrix](https://towardsdatascience.com/handling-sparse-matrix-concept-behind-compressed-sparse-row-csr-matrix-4fe6abe58a7a)
- [Bag of Words](https://docs.google.com/document/d/1QDDOoU0zo-uf9hGXHcOdNWiG7sq-pUPk0vAWLFeVi84/edit)
- [Tf-Idf Vectorizer](https://docs.google.com/document/d/1afbxNmhKSQrLCAHHjmjr7_Wqin31gj_xbkhIBvBDFlg/edit#)
- [Cosine similarity](https://www.machinelearningplus.com/nlp/cosine-similarity/#5softcosinesimilarity)

### transform_data():-
- transform_data() takes the value returned by combine_data() and the plot column from get_data() and applies CountVectorizer and TfidfVectorizer respectively and calculates the Cosine values.

### recommend_movies():-
- recommend_movies() takes four parameters i.e movie_name and return values of get_data(), combine_data(), transform_data as input and returns the top 20 movies similar to our input movie.

### results():-
- result() takes a movie's title as input and returns the top 20 recommendations using the recommend_movies() function.

<hr>

# Deployment folder Description:- 
## main.py
- The Flask app where we use the recommendation.py as a module and return the results in JSON format. 

## requirements.txt and .gitignore and setup.sh 
- This has all the dependencies required to deploy our application on Heroku

## Procfile
- A Procfile is a file which describes how to run your application.

## movie_dic.pkl and movie_ist.pkl 
- encoded data 

<hr> 

# Data set Folder :- 
- Contains the dataset we have used to build our recommendation system.
