# Sprint 2 - Yelp Restaurant Reviews rating

### By Steven Too Heng Kwee - 304449


### Tasks - Data preparation and predictive modelling

- This module contains the process undertaken to use the reviews data generated in sprint 1 , prepare the data and apply different model options.

#### Sprint 1 process:
- Installing Jupyter Notebook
- Installing MongoDB community edition with Robo3T 
- Installing Pymongoa and packages
- Extracting dataset fom Yelp and import into MongoDB
- Data processing and partitionning in MongoDB
- Pymongo client connection
- Retrieve Business and review file
- Cleaning text reviews
- EDA

### Getting Started

These instructions will get you a copy of the project up and running on your local machine. 

### Prerequisites

- Python v3
- Packages: pandas, numpy, nltk, Scikit-Learn

In case you need to install packages, do a "pip install <package name> from the anaconda concole.

### Data Used in this Analysis

review_TO_R.csv : File generated in sprint1 and stored in [https://github.com/stoohengkwee/CSDA-1050F18S1/tree/master/StevenToo-304449/data](https://github.com/stoohengkwee/CSDA-1050F18S1/tree/master/StevenToo-304449/data)


### Main characteristics of the dasatset:
- 102 MB store size
- 57047 reviews
- Restaurants='Toronto'
- Reviews posted date = '2018' 

We will be focus on the reviews (text) and rating (stars_x) features only
 

### Data preparation and modelling

Please see the notebook "Sprint2-Modelling-Copy2.ipynb"

### Tasks undertaken:
- (1). Importing all the necessary modules
- (2). Loading and seeing the dataset details
- (3). Classifying the dataset and splitting it into the reviews and stars
- (4). Data Cleaning for modelling
- (5). Vectorization of the whole review set and and checking the sparse matrix
- (6). Modelling
- (7). Sample application

Vectorization process has proven to be a very slow process impeding delivery of sprint 2. Coding optimizations will need to be performed.

### Results
- Multilayer Perceptron = 85.1%
- Multinomial Naive Bayes = 85.01%
- Random Forest Classifier = 73.7%
- Decision Tree = 70.07%
- Support Vector Machine = 57.48%


### Conclusion and Observation
- The positive reviews tend to lean towards 5 stars. This might be due to the dataset having more positive reviews as compared to negative reviews.
- Normalizing the dataset to have equal number of reviews might correct this.
- We are able to accurate predict the user star rating according to their reviews

### Next Step
- Wrap everything up. Create detailed document and presentation brief.

### Bucket list
- Review the vectorization process. Process takes too long.
- Review the whole modelling concept. Star rating prediction so far based on current ratings. Research to continue in getting a rating based on reviews and sentiment alone.


