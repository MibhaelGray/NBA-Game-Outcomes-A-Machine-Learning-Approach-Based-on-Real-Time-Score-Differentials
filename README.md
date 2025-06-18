# NBA Game Outcome Prediction
This project uses machine learning to predict NBA game outcomes based on real-time in-game statistics. Using data from the 2022-2023 NBA season (collected via nba_api), several models were trained—including logistic regression, random forest, gradient boosting, and SVM—to estimate the probability of a team winning at any point during a game.
Key Features:
Predicts win probability using features like score differential, time remaining, team win percentages, and momentum.
Removes overtime games for data consistency.
Compares multiple ML models; Gradient Boosting performed best (Accuracy: ~78%, ROC AUC: ~0.87).
Provides insights into which factors most influence NBA game outcomes.
Conclusion:
Score differential and team quality are the strongest predictors. The models show that even simple features can yield strong predictive performance for NBA game outcomes.
