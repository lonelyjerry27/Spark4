# Phishing Website Detection by Machine Learning Techniques
# Objective
A phishing website is a common social engineering method that mimics trustful uniform resource locators (URLs) and webpages. The objective of this project is to train machine learning models and deep neural nets on the dataset created to predict phishing websites. Both phishing and benign URLs of websites are gathered to form a dataset and from them required URL and website content-based features are extracted. The performance level of each model is measures and compared.
# Data Collection
The set of phishing URLs are collected from opensource service called PhishTank. This service provide a set of phishing URLs in multiple formats like csv, json etc. that gets updated hourly. To download the data: https://www.phishtank.com/developer_info.php. From this dataset, 5000 random phishing URLs are collected to train the ML models.

The legitimate URLs are obatined from the open datasets of the University of New Brunswick, https://www.unb.ca/cic/datasets/url-2016.html. This dataset has a collection of benign, spam, phishing, malware & defacement URLs. Out of all these types, the benign url dataset is considered for this project. From this dataset, 5000 random legitimate URLs are collected to train the ML models.
The above mentioned datasets are uploaded to the 'DataFiles' folder of this repository.
# Feature Extraction
The below mentioned category of features are extracted from the URL data:

1. Address Bar based Features
          In this category 9 features are extracted.
2. Domain based Features
          In this category 4 features are extracted.
3. HTML & Javascript based Features
          In this category 4 features are extracted.
The details pertaining to these features are mentioned in the URL Feature Extraction.ipynb.Open In Colab

So, all together 17 features are extracted from the 10,000 URL dataset and are stored in '5.urldata.csv' file in the DataFiles folder.
The features are referenced from the https://archive.ics.uci.edu/ml/datasets/Phishing+Websites.
# Models & Training
Before stating the ML model training, the data is split into 80-20 i.e., 8000 training samples & 2000 testing samples. From the dataset, it is clear that this is a supervised machine learning task. There are two major types of supervised machine learning problems, called classification and regression.

This data set comes under classification problem, as the input URL is classified as phishing (1) or legitimate (0). The supervised machine learning models (classification) considered to train the dataset in this project are:

Decision Tree
Random Forest
Multilayer Perceptrons
XGBoost
Autoencoder Neural Network
Support Vector Machines
All these models are trained on the dataset and evaluation of the model is done with the test dataset. 
# Data Files
This folder has the raw & extracted datafiles of this project. The description of each file is as follows:

1.Benign_list_big_final.csv: This file has list of legitimate urls. The total count is 35,300. The source of the dataset is University of New Brunswick, https://www.unb.ca/cic/datasets/url-2016.html.

2.online-valid.csv: This file is downloaded from the opensource service called PhishTank. This service provide a set of phishing URLs in multiple formats like csv, json etc. that gets updated hourly. To download the latest data: https://www.phishtank.com/developer_info.php.

3.legitimate.csv: This file has the extracted features of the 5000 legitimate URLs which are randonmly selected from the '1.Benign_list_big_final.csv' file.

4.phishing.csv This file has the extracted features of the 5000 phishing URLs which are randonmly selected from the '2.online-valid.csv' file.

5.urldata.csv This file is nothing but a combination of the above two files. It contains extracted features of 10,000 URLs both legitimate & phishing.
# End Results
From the obtained results of the above models, XGBoost Classifier has highest model performance of 86.4%. So the model is saved to the file 'XGBoostClassifier.pickle.dat'

Next Steps
This project can be further extended to creation of browser extention or developed a GUI which takes the URL and predicts it's nature i.e., legitimate of phishing. As of now, I am working towards the creation of browser extention for this project. And may even try the GUI option also. The further developments will be updated at the earliest.
