# Indians Diabetes Prediction

Use nine demographic/medical measurements to predict diabetes through a simple MLP with cross-validation and grid search.  
Credit: Deep Learning with Python by Jason Brownlee  
Data source UCL Machine Learning Repository
http://archive.ics.uci.edu/ml/machine-learning-databases/iris/iris.data

The dataset has 768 rows and 10 columns, column 1 to 9 are parameters, column 10 is prediction 0- no diabetes, 1-has diabetes
Column 1 - 9
1. Number of times pregnant.
2.  Plasma glucose concentration a 2 hours in an oral glucose tolerance test.
3.  Diastolic blood pressure (mm Hg).
4.  Triceps skin fold thickness (mm).
5.  2-Hour serum insulin (mu U/ml).
6.  Body mass index.
7.  Diabetes pedigree function.
8.  Age (years).
9.  Class, onset of diabetes within five years.

A simple 3-layer MLP was built with dense layers, loss function is binary cross entropy.
The following parameters were searched for optimization:   
optimizers = ['rmsprop', 'adam']  
inits = ['glorot_uniform', 'normal', 'uniform']  
epochs = [50, 100, 150]  
batches = [5, 10, 20]  

After the grid search, which took ~20 minutes to run on the local CPU, the following configuration generates the best result:  
Best: 0.748698 using {'batch_size': 5, 'epochs': 150, 'init': 'normal', 'optimizer': 'adam'}  

So the final accuracy is 0.75
