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
