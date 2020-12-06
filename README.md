
# Stat_426_final - Report

### Michael Pixton 12/10/2020

#### Question
The orginal question posed in my first update was changed to a new question; this one is related to Covid-19. How effective is testing in determinig the severtiy of Covid-19 and can the testing information be used to predict future outbreaks? To answer this question, data was collect from data.gov where Maryland has several datasheets with statewide covid-19 information. The Testing Volume and Total Hospitlizations were found to have potentially useful information and Maryland is a good sized location to perform a general test.

This data contains daily information about testing and counts of covid-19 hospitilizations. The testing data could be used to try and learn the hospilizations(metric for rating severness of covid=19) thus answering the question.

#### EDA
The data was read in, cleaned up and combined. We ended with a clean dataset with over 240 rows of information. Some summary statistics were calculated; interesting to note is that the standard devaition of Count(Hospitlizations) is 4889. Our model needs to do much better than this to be considered useful. A pairsplot was also generated; and looking at the Count row, we can already see some distinct correlations between some of our features and hospitlizations already.

#### Features and Model Creation
 Some features were generated that might make sense, such as a rolling 10-day average of positive covid-19 tests and a months column. Next, a series of models were fitted to the data with hyper parameters tuned to their best scores. The model with the higher R-squared score was a Ridge Regression Model. This model score .9924 on the testing data and .995 on the training data. 

#### Model Evaluation
The testing and training scores above show that our model seems to be quite accuarte but the mean absolute error score of 312, is far better than the standard deviation found previously. This means the our model is guessing off the actual number of hospilatization in the testing set by an average of 312 each time. This show good predictive power, using the mean of 12259 hospilizations, we are only erroring on average 3% off of that mean.  Inductive bias is introduced in this model purely due us picking the Ridge Regression model over some other Regression model. This bias could mean the model is better at certain feature situations and worse in other feature situations. This bias could be fixed by creating an ensemble that could reduce the bias from any singular model.

#### Question Answered
Our Ridge Regression Model shows strong learning when using testing statstics to guage severity of Covid-19. This model could be used to predict future hosplizations based on testing data. 