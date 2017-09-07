# Auspice

Included here are data and code for my Insight Data Science fellows project, Auspice. Auspice is a web app that predicts whether individual Twitter users will respond positively, negatively, or neutrally to a promoted tweet. You can use Auspice [here](http://www.auspiceapp.com/).

The Tweets directory contains the data set that was used to build the model behind Auspice. Models.ipynb is a Jupyter notebook that compares various models for predicting the sentiment of a Twitter user's response to a promoted tweet based on a set of approximately 300 features. The models considered include logistic regression, a random forest classifier, and a gradient boosting classifier.

The features used in these models are explained below. Many of the features were derived using GloVe vectors pre-trained on Twitter data. You can read more about GloVe and get the pre-trained vectors used in this project [here](https://nlp.stanford.edu/projects/glove/). Sentiment of replies was determined using VADER. You can read more about VADER [here](https://github.com/cjhutto/vaderSentiment) and [here](http://www.nltk.org/_modules/nltk/sentiment/vader.html). Results of VADER were mapped onto the classes *positive*, *neutral*, and *negative* using the VADER compound score. Replies with compound scores below -0.05 were classified as negative, replies with compound scores above 0.05 were classified as positive, and replies with compound scores between -0.05 and 0.05 were classified as neutral.

### Features

- **company\_type\_1**: Boolean value indicating whether the account publishing the promoted tweet is an account promoting a television series or movie.
- **company\_type\_2**: Boolean value indicating whether the account publishing the promoted tweet is an account related to a food product.
- **company\_type\_3**: Boolean value indicating whether the account publishing the promoted tweet is an account for a fast food chain.
- **company\_type\_4**: Boolean value indicating whether the account publishing the promoted tweet is an account for an enterprise-focused technology company or service.
- **company\_type\_5**: Boolean value indicating whether the account publishing the promoted tweet is an account for a consumer-focused technology company or service.
- **company\_type\_6**: Boolean value indicating whether the account publishing the promoted tweet is an account for a financial services company.
- **company\_type\_7**: Boolean value indicating whether the account publishing the promoted tweet is an account for a transportation-related company.
- **company\_type\_8**: Boolean value indicating whether the account publishing the promoted tweet is an account for a news media company.
- **company\_type\_9**: Boolean value indicating whether the account publishing the promoted tweet is an account for an energy company.
- **company\_type\_10**: Boolean value indicating whether the account publishing the promoted tweet is an account of a clothing company.
- **default\_profile\_image**: Boolean value indicating whether the account of the replier uses Twitter's default profile image.
- **demonstratives**: Count of demonstratives (i.e. *this*, *these*, *that*, *those*) in the initial promoted tweet.
- **followers\_count**: Count of users following the replier.
- **friend\_count**: Count of users the replier follows.
- **glove1\_dimx**: Mean value of GloVe dimension *x* of all words contained in replier's timeline (maximum 200 previous tweets) before tweet whose sentiment is to be predicted.
- **glove2\_dimx**: Mean value of GloVe dimension *x* of all words contained in timeline of company publishing promoted tweet (maximum 200 previous tweets) before promoted tweet in question.
- **glove2\_dimx**: Mean value of GloVe dimension *x* of all words contained in promoted tweet in question.
- **glove12\_cosine**: Cosine distance between mean GloVe vector representing replier's timeline and mean GloVe vector representing timeline of company publishing promoted tweet.
- **glove13\_cosine**: Cosine distance between mean GloVe vector representing replier's timeline and mean GloVe vector representing promoted tweet.
- **glove23\_cosine**: Cosine distance between mean GloVe vector representing timeline of company publishing promoted tweet and mean GloVe vector representing promoted tweet.
- **initial\_followers\_count**: Count of users following company publishing promoted tweet.
- **initial\_friends\_count**: Count of users company publishing promoted tweet follows.
- **initial\_has\_media**: Boolean value indicating whether promoted tweet contains media.
- **initial\_hashtag\_count**: Count of hashtags contained in promoted tweet.
- **initial\_mentions\_count**: Count of users mentioned in promoted tweet.
- **initial\_tweet\_sentiment**: Compound VADER sentiment of promoted tweet.
- **statuses\_count**: Count of statuses published by replier.
- **timeline\_sentiment**: Mean VADER compound sentiment of replier's timeline before reply to promoted tweet.
- **verified**: Boolean indicating whether replier is a verified Twitter user.
- **we**: Count of uses of *we* in promoted tweet.
- **you**: Count of uses of *you* in promoted tweet.

### References

Hutto, C. J. & Gilbert, E. E. (2014). VADER: A Parsimonious Rule-based Model for
Sentiment Analysis of Social Media Text. Eighth International Conference on
Weblogs and Social Media (ICWSM-14). Ann Arbor, MI, June 2014.

Pennington, J., Socher, R. & Manning, C. D. (2014) GloVe: Global Vectors for Word Representation.
