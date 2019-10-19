### Date created for project and README Files

Created the project file on: 21/08/19

Created the README file on: 07/09/19

***
### Project Title

**Wrangle and Analyse Data: WeRateDogs Twitter Data**
***
### Description

Real-world data rarely comes clean. Using Python and its libraries, I learned to gather data from a variety of sources and formats, assess its quality and tidiness, then eventually cleaning the data after identifying the issues. These tasks enhanced my data wrangling skills.

This project revolves around wrangling **WeRateDogs Twitter** data to create interesting and trustworthy analyses and visualisations. **WeRateDogs** is a Twitter account that rates people's dogs with a humorous comment about the dog. Additional gathering, then assessing and cleaning is required for functional analyses and visualisations.

The methodology I used for assessing data quality and then the solutions to clean the data came in the following three steps:
1. Gather - utlising a flat (csv) download, web scraping via requests and API programmatic download via the `Tweepy` python library.*
2. Assessing - mainly looking for issues within the dataset under **(1) data quality**, which identifies content issues such as missing data and **(2) data tidiness**, composed of structural issues that make the data untidy, hindering machine-readability as seen when there are multiple contents/observations in a row.
3. Cleaning - acting on the issues spotted during the assessment phase. I also utilised a sub 3 step process to implement these changes more clearly.
    - **Define** - document the issue and then signal what is going to be done
    - **Code** - use programming to fix the issue
    - **Test** - check that the change is in place and satisfies requirements

*Note - I could not authentically perform the API method of gathering some of the Twitter data, as for whatever reason, my developer client application was denied, leaving me with no keys for authentication. I will see in the future whether I can perform this process, which would be an additional feature. Nevertheless, Udacity realised these logistical issues and provided me the base file for which I could read in and transform the contents to a DataFrame, reassuring me that I could carry on the main process of practicing my data cleaning skills.

### Datasets
There were three datasets I had to take into consideration.

1. **Enhanced Twitter Archive (csv)** - columns included come from the master version for clarity.

* __tweet_id__ - used to identify the users. This was the only contents available across all three tables, to be used as a primary key.
*__timestamp__ - the time of the tweet
* __text__ - the twitter users' post containing comments about their respective dog.
* __rating_numerator__ - the maximum rating they gave. Some users were overly excitied, exceeding the conventional '10' scale. I took this into consideration when cleaning.
* __rating_denominator__ - conventionally out of '10', but again some users gave a rating below/above 10, for which I corrected eventually.
* __name__ - the name of the dog
* __dog_stage__ - illustrated the dog stage for each dog at the time of the tweet. The main issue came under data tidiness, as there were four values in four different columns with no defined variable. Instead, one variable (dog_stage) corresponding to these four different values would suffice.

2. **Image Predictions (tsv)** - information based on image predictions (top three) by a neural network algorithm, alongside each tweet ID. This was programmatically downloaded using requests.

* __p1__ - algorithm's #1 prediction for the image in the tweet.
* __p1_conf__ - how confident the algorithm is in its #1 prediction.
* __p1_dog__ - whether or not the #1 prediction is a breed of dog i.e. True/False.
* __p2__ - algorithm's second most likely prediction Labrador retriever.
* __p2_conf__ - how confident the algorithm is in its #2 prediction.
* __p2_dog__ - whether or not the #2 prediction is a breed of dog.
* __p3__ - algorithm's third most likely prediction Labrador retriever.
* __p3_conf__ - how confident the algorithm is in its #3 prediction.
* __p3_dog__ - whether or not the #3 prediction is a breed of dog.

3. **tweet_Json (txt)** - Using the tweet IDs in the WeRateDogs Twitter archive, this would require querying the Twitter API for each tweet's JSON data using Python's `Tweepy` library and store each tweet's entire set of JSON data in a file called tweet_json.txt file. Again, due to the above note, Udacity provided the file already for me to read in using the Python context manager. Tweet ID is included. I used `pandas` DataFrame to analyse the data.

* __retweet_count__ - each tweet's retweet country.
* __favorite_count ('like')__ - each tweet's favorite count.
