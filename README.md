# BENV0114

## Project introduction
This project tracks the visitors in Chinatown London from three perspectives, namely visitors' experiences, visitor number prediction and visitor positioning based on the data retrieved and scraped from Google Maps. The main findings and results from this project are as follows:

1. A language model based on BERT is built for local authorities and conservators to analyze visitors' experiences quantitatively, and a t-test is conducted concluding that visitors' experiences are positively related to cultural aspects of a site. 

2. A method based on the ratio of number of people visiting a site and number of comments on social media on this site is proposed to roughly estimate the number of visitors for a complex cultural heritage site which is composed of different independent sites. 

3. A dynamic heatmap in a week is made based on number of visiotrs of each site at different time, showing that the peak of visitor flow is in the evening of Saturday.

## Results presentation

#### 1. Language model

The comments and corresponding ratings collected can be used to make sentiment analysis to evaluate the visitors’ experiences. Firstly, those data are used to build a language model to conduct sentiment analysis on visitors' comments. To be more specific, Bidirectional Encoder Representations from Transformers BERT along with a Gated Recurrent Units (GRU) are chosen as the language model given its superior ability in recent NLP realm. Further, The dataset is split into training set, validation set and testing set, with a size of 15,849, 1000 and 1000 respectively. In its training phase, each comment can be viewed as an observation, and its corresponding rating can be seen as the target for the model. The words in each comment are tokenized in order to be fed into the model. The model has been trained with 10 epochs, and the best model was selected using the result from the validation set. In addition, despite of the predicting ability of the model, this model can also show the cosine similarity between words, which may be useful for further research.

Secondly, whether culture aspect has an influence on the visitors’ experiences is explored by analyzing the importance of each word in a given input comment to show the words that are vital for model’s prediction, and used BERT to find similarities between words.

![](https://github.com/sdyy6211/BENV0114-Chinatown/blob/master/NLP2.JPG?raw=true)

![](https://github.com/sdyy6211/BENV0114-Chinatown/blob/master/wordsimcom.PNG?raw=true)

#### 2. Prediction of annual visitor number with intervals

Since Chinatown is composed of different independent small sites, it is difficult to collect all the demographic data of the whole site. Therefore, a new method is proposed to roughly measure the number of visitors for each site based on the ratio of number of actual visiting and the number of comments of this place on Google Maps. Once this ratio has been estimated, the number of total visitors can be calculated by using the annual total number of comments of all sites in Chinatown on Google Maps. (The assumption of this method is that a visitor only visits one site in Chinatown in each tour)

![](https://github.com/sdyy6211/BENV0114-Chinatown/blob/master/pred_num.jpg?raw=true)

#### 3. Dynamic map of Chinatown London

Based on the estimated visitor number and popularity time retrieved from Google Maps, the heatmap can be produced.

![](https://github.com/sdyy6211/BENV0114-Chinatown/blob/master/dynamicmap.gif?raw=true)

## Codes and relevant data 

Note that as a result of data analysis, some files are no longer stored as described in the table of the assignment. Some csv files may 
have duplicated information, but they are uploaded because they may needed by different codes. Besides, some empty folder used to temporarily store scraped data are missing. They need to be created manually when used. 

1. The ***Codes*** folder contains all the codes used for this assignment.
Paths in the code files have to be changed when using the codes, and the chromedriver in selenium used to scraping data has to be downloaded from https://chromedriver.chromium.org/downloads. 

  - ***CHINATOWN_RETRIEVE.ipynb*** contains codes used to retrieve data from Google Maps official API

  - ***NLP_train.ipynb*** is used to train the BERT model
  
  - ***NLP_inference.ipynb*** is used for using BERT to make inferences and sentiment analysis on the collected data, this should be runned after using ***NLP_train.ipynb*** to train the model and get the ***bert2.pt*** file which contains trained parameters

  - ***getpopularity.ipynb*** retrieves popularity of each site from Google Maps

  - ***month_process.ipynb*** contains the codes of making the heatmap and visitor number prediction

  - ***scrapy_process.ipynb*** makes the t-test for the mean of two groups

  - ***scarpyv2.ipynb*** scrapes the comments from Google Maps
  
  - ***GOOGLEMAP_process.ipynb*** contains codes used to check whether places are within the Chinatown
  
  - ***xgboost_training.ipynb*** is the used to train the xgboost classifier

2. The ***NLP_training*** folder has the traning data for the BERT model.

3. The ***monthly comments*** folder contains comments within the latest month scraped from Google Maps

4. The ***popularity*** folder contains the popularity of each site in the Chinatown London

5. ***metadata.csv*** contains the metadata for each site, including their name, place id, coordinates, number of reviews, etc.

6. ***month_reviews.csv*** summarizes all the comments from the ***monthly comments*** folder

7. ***places.txt*** contains the names of all sites used in this assignment

8. ***pred_xgbc.csv*** contains the prediction results from the Xgboost classifier used before the first presentation

9. ***sum_alldata_extra_2.csv*** summarizes all the data in the ***NLP_training*** folder

10. ***num_reviews.csv*** records the number of reviews of each site per month

