# CS-M148
Dataset Used 
We used the Laptop Prices dataset, which contains information about different laptops and their specifications, such as price, brand, type, screen size, operating system, etc. It contains 1023 laptops and 23 features. 

Problem Statement 
We wanted to classify a laptop’s type (i.e. whether a laptop is a gaming laptop, 2-in-1 convertible, notebook, etc) given its specifications (amount of RAM, screen size, company, etc). 

Methodology 
We decided to use a random forest model for our multi-class classification of laptop type. It handles both numeric and categorical features well, and the dataset contains a mixture of both. It can also capture non-linear relationships and handle outliers due to it being an ensemble method that takes the output of multiple models into account. It also performed better than the other models we trained.

To further increase accuracy, we performed hyperparameter tuning. We compared different results after adjusting the number of trees, the maximum depth on each tree, the minimum number of samples required to split an internal node, and the minimum number of samples to be in a leaf node. To select the best combination of hyperparameters, we used grid search to identify the best value for each hyperparameter. Doing so evaluates every combination of the hyperparameter values, guaranteeing that we find the optimal model within the values we chose to search. After comparing results, the best-performing model had 32 trees, a maximum depth of 10, and a minimum sample split of 3. We also used a 5-fold cross-validation strategy, splitting the dataset into four training sets and one validation set for each iteration. This way, the model would be tested on different subsets to reduce overfitting. 

Results 
We achieved an overall test accuracy of 80.8%, meaning the model classified approximately 81% of the samples correctly. The majority class (Notebook) achieved the highest precision and recall score because it had the most examples that the model could train on. The classes with moderate support also achieved a decent recall. However, the classes with fewer than 10 examples (workstations and netbooks) perform poorly because of the lack of training data. As a result of the class imbalance, the macro average is lower (0.54) but the weighted average is relatively high (0.8). 
