# Kaggle_recipes

In this notebook I use the data provided in Kaggle's [Recipes Ingredients Dataset](https://www.kaggle.com/kaggle/recipe-ingredients-dataset) to train a machine-learning model to predict a dish's cuisine based on its ingredients.

### Technical details

**Data**
The training data contains roughly 30,000 dishes from 20 different cuisines. The classes are balanced and the test data contains ~10,000 instances.

**Data pre-processing**
1. Non-alphabetical characters are replaced by empty spaces and ingridients with more than one word are split into multiple words.

2. Wods/tokens are lemmatized to increase the homogeneity of the data (chopped -> chop)

3. Common ingredients which do not add much information are removed, such as 'fine', 'fresh' and color adjectives.

4. The target labels are encoded with OneHotEncoder.

**Word Embedding**

Tokens are vectorized using TFIDF. A minimum document occurency of 10 is imposed.

**Description of the machine learning algorithm**

A linear SVM model is adopted. This is because linear SVM models tend to perform well in NLP applications, where the embedded vectors lie in a high dimensional space. Parameter optimization is implemeted only for the regularization parameter 'C', due to computational limitations involved with using SVM models. A one-versus-rest classifier is used to train the model on the 20 different labels.


### Requirements
The following packages are necessary for this program, which I currently
run on Ubuntu 18.04.2 LTS. See installations tips below.
```
pandas
numpy
matplotlib
sklearn
nltk
```
