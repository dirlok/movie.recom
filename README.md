# movie.recom
AIM:
   To build a movie recommendation engine with four different models.
   1)Simple recommendation engine.
   2)Content based recommendation engine.
   3)Collaborative filtering based recommendation engine.
   4)Hybrid recommendation engine.
   
Datasets are gather with the help of Movielens.
Dataframe: Credits,Keyword,Links,Metadata,Rating
Data wrangling helps us to convert data from json to csv format.

1)SIMPLE RECOMMENDATION ENGINE:
    The Simple Recommender offers generalized recommendations to every user based on movie popularity and (sometimes) genre.
    The basic idea behind this recommender is that movies that are more popular and more critically acclaimed will have a higher probability of being liked by the average audience.
    This model does not give personalized recommendations based on the user,we create a rating method called "weighted rating" and we will create a percentile table ,based on this rating the movie will qulify and recommended for the users.

2)CONTENT BASED RECOMMENDATION ENGINE:
    Using movie description, taglines, keywords, cast, director and genres
    Description= overview + taglines
    What I plan on doing is creating a metadata dump for every movie which consists of genres, director, main actors and keywords.
    I then use a "Count Vectorizer" to create our count matrix.
    The "Tfidf vectorizer" is used calculate the number of common words occured in the tagline.Uncommon words in a movie has higher tfidf and it is arranged in descesding
    order.
    calulating the "cosine_sim":I will take the top 25 movies based on similarity scores and calculate the vote of the 60th percentile movie.
    The remaining steps are similar to what we did earlier: we calculate the cosine similarities and return movies that are most similar.

3)COLLABORATIVE FILTERING BASED RECOMMENDATION ENGINE:
    Our content based engine suffers from some severe limitations.
    It is only capable of suggesting movies which are close to a certain movie. That is, it is not capable of capturing tastes and providing recommendations across    
    genres.
    Also, the engine that we built is not really personal in that it doesn't capture the personal tastes and biases of a user. Anyone querying our engine for
    recommendations based on a movie will receive the same recommendations for that movie, regardless of who (s)he is.
    Therefore, in this section, we will use Collaborative Filtering to make recommendations to Movie Watchers. Collaborative Filtering is based on the idea that users     similar to a me can be used to predict how much I will like a particular product or service those users have used/experienced but I have not.
    I will not be implementing Collaborative Filtering from scratch. Instead, I will use the Surprise library that used extremely powerful algorithms like Singular         Value Decomposition (SVD) to minimise RMSE (Root Mean Square Error) and give great recommendations.
 
 4) HYBRID RECOMMENDATION ENGINE:
     In this section, will try to build a simple hybrid recommender that brings together techniques we have implemented in the content based and collaborative filter        based engines. This is how it will work:
     Input: User ID and the Title of a Movie.
     Output: Similar movies sorted on the basis of expected ratings by that particular user.
     
     
     ALL THE FORMULAS AND ITS APPLICATION ARE MENTIONED IN DETAIL IN THE CODE SECTION:
