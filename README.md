# BENV0114

#### These are codes and relevant data for the assignment of BENV0114

Note that as a result of data analysis, some files are no longer stored as described in the table of the assignment. Some csv files may 
have duplicated information, but they are uploaded because they may needed by different codes.

1. The ***Codes*** folder contains all the codes used for this assignment.
Paths in the code files have to be changed when using the codes, and the chromedriver in selenium used to scraping data has to be downloaded from https://chromedriver.chromium.org/downloads. 

  - ***CHINATOWN_RETRIEVE.ipynb*** contains codes used to retrieve data from Google Maps official API

  - ***NLP_inference.ipynb*** is used for using BERT to make inferences and sentiment analysis on the collected data

  - ***NLP_train.ipynb*** is used to train the BERT model

  - ***getpopularity.ipynb*** retrieves popularity of each site from Google Maps

  - ***month_process.ipynb*** contains the codes of making the heatmap and visitor number prediction

  - ***scrapy_process.ipynb*** makes the t-test for the mean of two groups

  - ***scarpyv2.ipynb*** scrapes the comments from Google Maps

2. The ***NLP_training*** folder has the traning data for the BERT model.

3. The ***Monthly comments*** folder contains comments within the latest month scraped from Google Maps

4. The ***Popularity*** folder contains the popularity of each site in the Chinatown London

5. ***metadata.csv*** contains the metadata for each site, including their name, place id, coordinates, number of reviews, etc.

6. ***month_reviews.csv*** summarizes all the comments from the ***Monthly comments*** folder

7. ***places.txt*** contains the names of all sites used in this assignment

8. ***pred_xgbc.csv*** contains the prediction results from the Xgboost classifier used before the first presentation

9. ***sum_alldata_extra_2.csv*** summarizes all the data in the ***NLP_training*** folder

10. ***num_reviews*** records the number of reviews of each site per month
