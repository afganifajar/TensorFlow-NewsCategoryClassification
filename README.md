# TensorFlow-NewsCategoryClassification
News category classification from the news text using Bidirectional LSTM on TensorFlow

This notebook was used as one of my submission in Dicoding's learning class.

The dataset that used in this project is obtained from Kaggle public dataset.
Dataset link: https://www.kaggle.com/datasets/setseries/news-category-dataset

To run this project properly, there are several libraries that needed to imported first. If it's not on your default system, please install it first with pip command. List of libraries that used on this project consist of:
1. numpy
2. pandas
3. matplotlib
4. TensorFlow
5. SKLearn

The project starts by importing dataset csv into pandas. Since we will only detect category from the news text, we only need to use 'category' and 'short_description' column. There are 5 categories that will be used on this project, which consist of: Business, Entertainment, Politics, Sports, and Wellness. Each category then is converted into number format from 0-4 for labelling purpose.

The text and the category then splitted into training and test set with proportion of 80:20. Both set then converted into sequence form and padded using Tensorflow sequence function. In this form, we can safely used it as training data and validation data.

The model used in this notebook is Bidirectional LSTM followed by some dense/fully-connected layers that already embedded in the beginning. The final activation function is using Softmax and followed by loss calculation using sparse crossentropy and optimized using Adam. The model also applying callback so the training can stop when both accuracy already reach 80% for training and 75% for testing.

In the end of the code, I put one test data using a news about witcher 3, that correctly predict that it's should be categorized as entertainment.
