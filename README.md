# Video_Game_Sales

# Motivation

Seeing how popular a video game will do in a region is an important factor to consider when marketing your video game. Do you want to spend more money marketing the game in North America or Europe? That's the question this projecrt aimed to answer. This project, however, answered it in a different way rather than focusing on sales. This project looked at the popularity trends of game criterias to predict whether a game will be more successful is North America(NA) or Europe(EU) through various classification models.

# Data Source

The data was obtained through kaggle and the University of Portsmouth dataset. Both datasets can be found through the "/data/cleaning_data/" path.

Actions that took place During Data Cleaning:
- Feature Dropping
- Feature Renaming
- Placeholder/Null Values Replacement
- Null Value Row Dropping
- Dataset Merging

The dataset after cleaning and combining can be found through the "data/cleaned_video_game.csv" path

### Target

The variable which this project is trying to predict is whether North American sales and greater than European sales for a given game, "NA_Sales_More_Eu".

# Exploratory Data Analysis
(The process for the EDA can be found in the "EDA.ipynb" notebook)

By Visualizing, we were able to attain insights about the lengths we can take our dataset as well as explore possible ways to improve model performance.

From the histogram below, we attain information about how North Americans spend much more on games compared to Europeans. We also find out about a class imbalance in our dataset which needs to be addressed.
<img src="pictures/Image%205-9-19%20at%201.34%20PM.jpg" height="300">


These two graphs about Genre and ESRB Rating for North America and Europe allows us to see that Genre and ESRB_rating are relevant predictors because there are slight differences about the genre and ESRB Rating, in terms of region percentages, that each region tends to sway towards. 
<img src="pictures/Image%205-9-19%20at%201.51%20PM.jpg">


Although these graphs are appealling, they showed the extent to which we can take our data as there was no way to compare North America's performance to Europes in terms of sales and publishers. We only knew whether North America bought more of a game than Europe, which is the target variable.
<img src="pictures/Image%205-9-19%20at%201.52%20PM.jpg" width="1300">


After doing some feature engineering where we create dummy variables and add more features, we select a subset of those features. This dataset is compared against the original with some dummy variables to see which dataset performs better. The original dataset with some dummy variables performed better which is the final dataset used for model testing. This dataset is labeled "modeling_video_game_dataset.csv".

# Modeling
(The process for the modeling can be found in the "Modeling.ipynb" notebook)

The models that will be attempted to reach the best results are:
- Logistic Regression
- K Nearest Neighbors
- Decision Trees
- Random Forest
- XGBoost

### Baseline

Random Forest and XGBoost performed the best out of all with the highest f1 scores and lowest percentages of errors in terms of False Positives and False Negatives.
<img src="pictures/Image%205-9-19%20at%202.27%20PM.jpg" height="250">


### After Hyperparameter Tuning

XGBoost was found to be the best predicting model. The model does not seem too overfit as teh F1 scores are around the same area. This model also performed the best in terms of the lowest amount of False Negatives, as it was worrying that there was a class imbalance in the test set. This better ratio of Predicted Negatives to Actual Negatives lead to a higher Acurracy score compared to other tuned models as well.

<img src="pictures/Image%205-9-19%20at%207.43%20PM.jpg" height="400">

# Things to Consider in the Future

The scope of my project was limited to the dataset here. There are features which would definitely help in predicitng whether NA sales for a particular game is going to be greater than EU games for the same game such as the population distribution and age distribution. To the this project to the next step, data such as the ones just mentioned be be obtained and factored in.
