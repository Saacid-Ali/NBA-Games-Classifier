# NBA Games Classifier: Project Overview 
* Created a tool that estimates the outcome of NBA games.
* Combined a dataset from Kaggle with NBA All-Star data scrapped from the web.
* Utilised Logistic Regression, Random Forest, and Support Vector Machine classifiers to decide on the best model.

## Code and Resources Used 
**Python Version:** 3.7.6  
**Packages:** pandas, numpy, sklearn, matplotlib, plotly    
**Data Collection Source:** https://www.kaggle.com/nathanlauga/nba-games     
**Scrapped Website:** https://basketball.realgm.com/nba/allstar/game/rosters    
**Scraper Article Tutorial:** https://www.freecodecamp.org/news/how-to-scrape-websites-with-python-and-beautifulsoup-5946935d93fe/  

## Web Scraping
Created a web scraper to scrap RealGM - Basketball for their NBA All-Star data which included:
* Player names
* Teams the players played for
* Years of selection
* Selection type

## Data Collection
The data was collected from https://www.kaggle.com/nathanlauga/nba-games. The data came with 5 datasets but for the purposes of this project only 1 dataset was used which was 'games.csv'.

This dataset contains data from NBA games between October 2003 - March 2020 and includes some of the following data:
*	Home/Away Team Points
* Home/Away Team Assists
*	Home/Away Team Rebounds
* Home/Away Team Field Goal %
*	Home/Away Team 3pt %
* Home/Away Team Free Throw %

## Data Cleaning
Once the data was collected from Kaggle and the All-Star data was scraped from RealGM, the data needed to be cleaned prior to being used in the models. I made the following changes:

* Changed the team names of some of the NBA All-Stars as the team names changed in real life such as the New Jersey Nets being renamed the Brooklyn Nets  
* Removed the rows without game data.
* Added a Home Team and Away Team All-Stars columns to the 'games.csv' dataset which is the total number of All-Stars playing for the teams in that game.
* Changed the Home/Away Team IDs to the team names using the data from 'teams.csv'.

## EDA and Data Analysis
I looked at the distributions of the data and the value counts for the various categorical variables and also analysed the data to identify key trend. Below are a few highlights.

![alt text](https://github.com/Saacid-Ali/NBA-Games-Classifier/blob/master/Boxplot_1.png)
![alt text](https://github.com/Saacid-Ali/NBA-Games-Classifier/blob/master/Boxplot_2.png)
![alt text](https://github.com/Saacid-Ali/NBA-Games-Classifier/blob/master/All_Star_Distribution.png)
![alt text](https://github.com/Saacid-Ali/NBA-Games-Classifier/blob/master/Win_percentage_by_All-Stars.png)

## Model Building 

Firstly, I dropped some variables from the training data which included Home/Away team points, Season and the Home_Team_Wins variable. The test data only included the Home_Team_Wins variable as this is what I aimed to predict. 

Furthermore, I split the data into train and tests sets with a test size of 20%.   

I tried three different models and evaluated them using different metrics such as Model Score, Recall Score, Precision Score and F1 Score. I also illustrate the performance of each model with a confusion matrix. I chose these different metrics because simply choosing one metric to evaluate the performance of these models does not paint the full picture of how well each model performed.

I tried three different models:
*	**Logistic Regression** 
*	**Random Forest** 
*	**Support Vector Machine**  

Below is a graphic of the importance of each feature which found using Random Forest.

![alt text](https://github.com/Saacid-Ali/NBA-Games-Classifier/blob/master/Feature_importance.png)


## Model performance

The Support Vector Machine model slightly outperformed the other two models with a higher Model Score and F1 Score.
The Logistic Regression Model and Support Vector Machine Model had the same Recall Score and the Random Forest Model had the highest Precision Score.

However, the performance of the 3 models were extremely similar as evident in the figures below.

![alt text](https://github.com/Saacid-Ali/NBA-Games-Classifier/blob/master/Peformance_Evaluation.png)
![alt text](https://github.com/Saacid-Ali/NBA-Games-Classifier/blob/master/Model_scores.png)
![alt text](https://github.com/Saacid-Ali/NBA-Games-Classifier/blob/master/Performance_metrics.png)

