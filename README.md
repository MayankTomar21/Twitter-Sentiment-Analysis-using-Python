# Twitter-Sentiment-Analysis-using-Python
Sentiment Analysis is the process of ‘computationally’ determining whether a piece of writing is positive, negative or neutral. It’s also known as opinion mining.

Why sentiment analysis?

1.Business: In marketing field companies use it to develop their strategies, to understand customers’ feelings towards products or brand, how people respond to their campaigns or product launches and why consumers don’t buy some products.
2.Politics: In political field, it is used to keep track of political view, to detect consistency and inconsistency between statements and actions at the government level. It can be used to predict election results as well!
3.Public Actions: Sentiment analysis also is used to monitor and analyse social phenomena, for the spotting of potentially dangerous situations and determining the general mood of the blogosphere.

Installation:

Tweepy: tweepy is the python client for the official Twitter API. Install it using following pip command:
pip install tweepy
TextBlob: textblob is the python library for processing textual data. Install it using following pip command:
pip install textblob
Also, we need to install some NLTK corpora using following command:
python -m textblob.download_corpora
(Corpora is nothing but a large and structured set of texts.)
Authentication: In order to fetch tweets through Twitter API, one needs to register an App through their twitter account. Follow these steps for the same:

Open this link and click the button: ‘Create New App’
Fill the application details. You can leave the callback url field empty.
Once the app is created, you will be redirected to the app page.
Open the ‘Keys and Access Tokens’ tab.
Copy ‘Consumer Key’, ‘Consumer Secret’, ‘Access token’ and ‘Access Token Secret’.

Implementation: 

We follow these 3 major steps in our program:

Authorize twitter API client.
Make a GET request to Twitter API to fetch tweets for a particular query.
Parse the tweets. Classify each tweet as positive, negative or neutral.
Now, let us try to understand the above piece of code:

First of all, we create a TwitterClient class. This class contains all the methods to interact with Twitter API and parsing tweets. We use __init__ function to handle the authentication of API client.
In get_tweets function, we use:
fetched_tweets = self.api.search(q = query, count = count)
to call the Twitter API to fetch tweets.
In get_tweet_sentiment we use textblob module.
analysis = TextBlob(self.clean_tweet(tweet))
TextBlob is actually a high level library built over top of NLTK library. First we call clean_tweet method to remove links, special characters, etc. from the tweet using some simple regex. Then, as we pass tweet to create a TextBlob object, following processing is done over text by textblob library:
Tokenize the tweet ,i.e split words from body of text.
Remove stopwords from the tokens.(stopwords are the commonly used words which are irrelevant in text analysis like I, am, you, are, etc.)
Do POS( part of speech) tagging of the tokens and select only significant features/tokens like adjectives, adverbs, etc.
Pass the tokens to a sentiment classifier which classifies the tweet sentiment as positive, negative or neutral by assigning it a polarity between -1.0 to 1.0 .
TextBlob uses a Movies Reviews dataset in which reviews have already been labelled as positive or negative.
Positive and negative features are extracted from each positive and negative review respectively.
Training data now consists of labelled positive and negative features. This data is trained on a Naive Bayes Classifier.
Finally, parsed tweets are returned. Then, we can do various type of statistical analysis on the tweets. For example, in above program, we tried to find the percentage of positive, negative and neutral tweets about a query.


Full Code Explanation:

The code first creates a RandomForestRegressor object.
This object is used to train a model that predicts air quality index (AQI) values.
Next, the code separates the class label (train) and other attributes (target).
The train data set contains information about air quality index values for different classes, while the target data set contains only AQI values.
The code then fits the RandomForestRegressor object on the train data set and targets the predicted AQI value in the target data set.
The code creates a model using the RandomForestRegressor algorithm.
The model is fit to data consisting of air quality index values from training data and target values for air quality index.
The code in this section is used to train a Random Forest Regressor.
A Random Forest Regressor is a machine learning algorithm that uses a collection of trees (or forests) to make predictions.
The first thing the code does is set some parameters.
The most important parameter is the bootstrap parameter, which determines how often the training data should be randomly sampled from.
The default value is True, which means that the training data will be randomly sampled every time it’s needed.
Another important parameter is ccp_alpha, which controls how much weight should be given to features when making predictions.
By default, ccp_alpha is set to 0.0, which means that all features are equally important when making predictions.
However, if you want more weight to be given to certain features over others, you can set ccp_alpha to a value between 0 and 1 .
If you set ccp_alpha too low (i.e., less than 0), then the feature with the lowest importance will have the most weight in predicting outcomes; if you set ccp_alpha too high (i.e., greater than 1), then the feature with the highest importance will have the most weight in predicting outcomes.
The next thing
The code will create a Random Forest Regressor to predict sales.
The Random Forest Regressor will use bootstrap sampling to generate samples, and will have a criterion of mse.
The Random Forest Regressor will also have a max_depth and max_features parameter.
The max_depth parameter controls the maximum number of layers in the Random Forest Regressor, while the max_features parameter controls the number of features that are used in the model.
Finally, the code specifies that the Random Forest Regressor should have a min_impurity_decrease and min_impurity_split parameter.
These parameters control how aggressively the model should try to reduce impurity (i.e., variance).
Lastly, the code specifies that the Random
The code begins by importing the necessary modules.
The AdaBoostRegressor module is used to create and fit the model.
The learning_rate, loss, and n_estimators parameters are all optional; they can be left at their default values (1.0, ‘linear’, and 50, respectively).
Next, the base_estimator parameter is set to None.
This means that the model will be fitted using a random forest algorithm instead of a simple linear regression model.
The next step is to define the model parameters.
The learning_rate parameter sets how often the algorithm should learn from data; it should be greater than 1 but less than or equal to 2 (in this case, 1.0).
The loss parameter specifies how much weight each prediction should have in determining the final score; it should be ‘linear’ in this case (meaning that predictions with lower scores will have less impact on the final score).
Finally, n_estimators defines how many trees will be used in the random forest algorithm; 50 is used here.
After defining these parameters, it’s time to fit the model!
First, train1 and target are passed into the fit() method as input data.
Next, m2
The code first imports the AdaBoostRegressor module.
This module allows you to train a model using a gradient descent algorithm.
Next, the code defines the model using the AdaBoostRegressor() function.
The parameters that are defined include the base estimator (which is None in this case), learning rate (1.0), and loss (linear).
Finally, the code sets up 50 training iterations and passes in the target value as an input.
After fitting the model, the predicted values for each sample are returned.
