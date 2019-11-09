### Date created for project and README Files

Created the project file on: `21/08/19`

Created the README file on: `07/09/19`

***
### Project Title

**Wrangle and Analyse Data: WeRateDogs Twitter Data**
***
### Description

Real-world data rarely comes clean. Using Python and its libraries, I learned to gather data from a variety of sources and formats, assess its quality and tidiness, then eventually cleaning the data after identifying the issues. These tasks enhanced my data wrangling skills.

This project revolves around wrangling **WeRateDogs Twitter** data to create interesting and trustworthy analyses and visualisations. **WeRateDogs** is a Twitter account that rates people's dogs with a humorous comment about the dog. Additional gathering, then assessing and cleaning is required for functional analyses and visualisations.

The methodology I used for assessing data quality and then the solutions to clean the data came in the following three steps:
1. Gather - utilising a flat (csv) download, web scraping via requests and API programmatic download via the `Tweepy` python library.*
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
* __timestamp__ - the time of the tweet
* __text__ - the twitter users' post containing comments about their respective dog.
* __rating_numerator__ - the maximum rating they gave. Some users were overly excited, exceeding the conventional '10' scale. I took this into consideration when cleaning.
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

### Findings

**N.B** - final findings are based on sample sizes - **tweet IDs** - of 2086 (twitter archive) and 2075 (image predictions).

- Around 80% of users (at least 1600) gave the highest rating (10) to the dogs tweeted, suggesting that WeRateDogs is a popular account among users based on views/follows.
- The most popular breed ranked in terms of tweets is the Golden retriever with 150 references.
- Given the tweet coverage from 2015-2017, both average retweet and favorite count for the WeRateDogs twitter page increased on average per year.
    - retweet count - increased from around 1080 (2015) to 6357 (2017).
    - favorite count - increased from around 2492 (2015) to 22209 (2017).
- Based on the relationship of favorite count on retweet count, there exhibits a reasonably ***strong*** **positive correlation**, given a correlation coefficient of 0.79.
    - It is reasonable to suggest that as the favorite count increases, the retweet count also increases.

### Files used

Although this is mainly Twitter data, Udacity provided most of resources/guidance for acquiring and wrangling the various file types.
* [twitter-archive data - original](<https://drive.google.com/open?id=1fgmaLdYH_h4O2lgNhjfs0N8lPn_LOBM_hVrWeE2WwXc>)
* [twitter-archive data - cleaned](<https://drive.google.com/open?id=1gqubT4uVYcxV8dOS1LiSprEFwxD_on4UyXWuf7VtOkA>)
* [image-predictions data](<https://drive.google.com/open?id=1yXNL8glNqEgyxYEfxrXTURXadE_jA6UL>)
    * [Udacity cloud link](<https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv>)
* [tweet-json data - favorite and retweet count](<https://drive.google.com/open?id=1jlxi7QZcBILFy73163RvAEG3iwUM_pwx>)

### References

Beyond my Udacity mentor, peers and lectures, I consulted a number of resources including:

* [Reading and Writing JSON to a File in Python](<https://stackabuse.com/reading-and-writing-json-to-a-file-in-python/>)
* [Tweepy Documentation](<https://buildmedia.readthedocs.org/media/pdf/tweepy/latest/tweepy.pdf>)
* [WeRateDogs Twitter page](<https://twitter.com/dog_rates?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor>)
* [Wickham (2014) - Tidy data](https://cran.r-project.org/web/packages/tidyr/vignettes/tidy-data.html)
* [McKinney (2017) - Python for Data Analysis 2e, see chapters 6-8](https://wesmckinney.com/pages/book.html)
* [DataCamp - Cleaning Data in Python](<https://www.datacamp.com/courses/cleaning-data-in-python>)
