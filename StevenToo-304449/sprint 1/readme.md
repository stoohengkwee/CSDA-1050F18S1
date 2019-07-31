# Sprint 1 - Yelp Restaurant Reviews odule containsto gather data according to the research question, prepare the data and perform same exploratory analysis.

### Research Question

- Analysing the reviews and star rating set by reviewers.  Did they provide a proper rating? Can we detect the inconsistencies and provide a more accurate rating instead? 

### Getting Started

These instructions will get you a copy of the project up and running on your local machine. 

### Prerequisites

- Python v3 and Pymongo package.

Other basics packages: pandas numpy plotly textblob nltk wordcloud seaborn matplotlib.

In case you need to install packages, do a "pip install <package name> from the anaconda concole.

- MongoDB Community edition, Robo3t or Studio 3T
Download and install from [https://www.mongodb.com/download-center/community](https://www.mongodb.com/download-center/community)

- Robo3t or Studio 3T from [https://robomongo.org/](https://robomongo.org/)

### Data Used in this Analysis

Yelp provides a complete academic dataset at [https://www.yelp.ca/dataset](https://www.yelp.ca/dataset)

The whole set is a 5.6 GB TAR file. This TAR file contained second TAR file that must be extracted to get a series of JSON files: business, checkin, photos, review, tip, and user. Total real size is 8.05 GB.

### Main characteristics of the dasatset:
- 6.6M reviews
- 192k businesses
- 10 metro areas

We will be focusing on the following files:
Business.json: 131 Mb.  Contains business data including location data, attributes, categories and average star rating. 

Review.json: 4.97 Gb.  Contains full review text data including the user_id that wrote the review and the business_id the review is written for.

#### Data processing
Due the size of the files which makes them impossible to load directly into a Pandas dataframe, MongoDB is used a the repository and segmention tool as follows
- Database "bigdata" created
- Business.json imported in collection "business"
- Review.json imported into collection "reviews_bulk"
- Collection "business" was segmented into "business_TO_R" for restaurants in Toronto

```
db.getCollection('business').find({$and:[{'categories':{$regex: '.*Restaurants.*'}},{'city':'Toronto'}]})
```
- Collection "reviews_bulk" was segmented into "reviews_2018" for reviews in 2018

```
db.getCollection('reviews_bulk').find({'date':{$regex:'2018'}})
```

#### MongoDB bypass

To allow for Python Notebook to run without MongoDB repository, the segmented datasets were saveed into csv file and posted on [https://github.com/stoohengkwee/CSDA-1050F18S1/tree/master/StevenToo-304449/data](https://github.com/stoohengkwee/CSDA-1050F18S1/tree/master/StevenToo-304449/data)
Please unzip and post the files in the same folder as the ipynb file.

#### Insights and visualizations

Please see the notebook "sprint1-DataExplore-pymongo.ipynb"

In summmary, the rating distribution by show a normal distribution where as the rating distribution from reviewers show a concentration towards the 5 and 1 stars. This show that yelp is using other features in its rating and reviewers might not be providing a fair logical rating.    


#### Next Steps

Further use of the pymongo package and more exploratory analysis work on the attributes to be added for general insights.  Those will be investigated depending on outcomes of the text anaylsis in sprint 2 and 3.  However the bulk of the analysis and modeling will be on the reviews themselves with the use of NLP, word count, bagging and sentiment to establish the relationship with the star rating.

