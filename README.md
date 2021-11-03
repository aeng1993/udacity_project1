# Udacity_Proj1_SeattleAirbnb
analysis based on Seattle airbnb listing data - project 1 for data scientist nanodegree (Udacity)

(1) Installations

The code was written in Jupyter Notebook 6.3.0 from Anaconda 2.0.3
Several libraries are used in the code file:
   - pandas
   - numpy
   - matplotlib
   - re
   - sklearn.ensemble
   - sklearn.model_selection
   - sklearn.feature_extraction.text 
   - gensim
   
   
(2) Project Motivation

This project aims to gain business insights on the Seattle airbnb rental market by looking at calendar and listing data from a dataset of Seattle airbnb rental listing.
I aim to answer the following questions:
   (a) What are the busiest times of a year to visit Seattle? How much price spike?
   (b) What is the vibe for some of the popular neighbourhood based on listing description?
   (c) How should a host set rental price based on rental listing info? 
   (d) What are the key features that influence the rental listing price?
   
(3) File Descriptions

The data files include:
   - calendar, listings, reviews files for Seattle airbnb listings scrapped in 01/04/2016.
   - ""seattle_airbnb.ipynb" the main file for answering all above questions

(4) Project Conclusions/Summary

There are three parts in the project:

(a) What are the busiest times of a year to visit Seattle? How much price spike?
The calendar data is analysed for the Seattle listings. The monthly-average listing price for all available listings is calculated and plot as a function of time. The price per person is also calculated based on "accommodates" data and "price" data. The avearge price is found to reach the peak around July, the summer time, and goes lower later in the year. The price in July could be 25% higher than January level. However, note that the analysis is done using the calendar price data found in January time. So the "July" price is the price one would pay if they book at the time of January. The price may vary at later point in time before July as the demand/supply balance changes.
       
(b) What is the vibe for some of the popular neighbourhood based on listing description?
The "neighbourhood overview" about each listing is used for this analysis. The "neighbourhood overview" for all listings in each neighbourhood are combined as a document, and all the documents from different neighbourhood are used to find 3 "topics" using LDA model. Based on the model output, the 3 "topics" are found to be nature scenery (green lake, trail, garden, etc.), tourist attractions (pike market, space needle, etc.), city life (night life, museum, art, etc.)
Most documents are found to have a major topic that has a >85% contribution. So the neighbourhood "vibe" can naturally be described by the major topic (1 of the 3  above). Then, the popular neighborhood with >60 listings are summarized based on their "vibe"/topic.

(c) How should a host set rental price based on rental listing info? 
(d) What are the key features that influence the rental listing price?
Features are first selected from the dataset and a random forest regressor is trained to predict the listing price. The numerical features are processed as needed, and dummy variables are created for the categorical features. Missing values are treated (e.g. NAN for "cleaning fee" is considered as no cleaning fee, so set to 0)
The regressor has a 88% r2 score for training test and a 67% r2 score for test set, which is not ideal but should be good enough for the purpose of a rough analysis. The number of bedrooms is found to be the most important feature that affects the listing price. 

(5) Licensing, Authors, Acknowledgements

The airbnb data is provide by Airbnb in Kaggle.
https://www.kaggle.com/airbnb/seattle/data 
https://www.kaggle.com/airbnb/boston/data 
       
