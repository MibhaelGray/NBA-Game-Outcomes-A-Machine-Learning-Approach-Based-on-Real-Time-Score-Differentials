# NBA Game Outcome Prediction: A Machine Learning Approach Based on Real-Time Score Differentials

## Overview

This project analyzes NBA game data to build predictive models that can determine game outcomes based on in-game statistics. The analysis uses detailed "snapshots" of games at regular time intervals, tracking scores, time remaining, and other metrics throughout each game to predict which team will win.

## Key Insights

- **Dynamic Game Nature**: Most NBA games remain competitive until late in the contest, with both the size and timing of leads playing crucial roles in determining win probability
- **Home Court Advantage**: The impact of home court advantage fluctuates throughout the game, with the distribution of score differentials being approximately normal (suggesting blowouts are equally likely for both home and away teams)
- **"No Lead is Safe"**: Even large leads in early quarters don't guarantee victory, with win probability only reaching around 61% for the largest leads in the first quarter

## Data Source

The project uses NBA game data collected via the `nba_api` Python package, providing direct access to NBA.com's official statistics. The dataset contains snapshots from the 2022-2023 NBA season with features including:
- Score differentials
- Time remaining
- Period information
- Team win percentages
- Momentum indicators

## Methodology

### Data Preprocessing
- Removed overtime games to maintain data consistency
- Engineered momentum features based on score differential changes
- Handled missing values systematically
- Split data by unique games (not individual snapshots) to prevent data leakage

### Models Implemented
1. **Logistic Regression** - Baseline linear model
2. **Random Forest** - Ensemble tree-based approach
3. **Gradient Boosting** - Advanced ensemble method
4. **Support Vector Machine** - Linear SVM with calibration

### Model Performance
All models performed remarkably similarly, with the best model (Gradient Boosting) achieving:
- **Test Accuracy**: 78.29%
- **ROC AUC**: 0.8684

## Key Findings

1. **Score Differential is King**: The strongest predictor of game outcomes (correlation: 0.577)
2. **Team Quality Matters**: Home and away team win percentages show moderate predictive power
3. **Time is Less Important**: Surprisingly, time elapsed has virtually no correlation with outcomes
4. **Model Robustness**: All four models achieved ROC AUC scores above 0.86, suggesting clear patterns in the data

## Technical Implementation

- **Cross-Validation**: Used GroupKFold to ensure proper game-level splitting
- **Hyperparameter Tuning**: Comprehensive grid search for each model type
- **Feature Engineering**: Created momentum indicators and standardized all features
- **Model Persistence**: Saved trained models using joblib for future use

## Conclusion

The project successfully demonstrates that in-game statistics can be highly predictive of NBA game outcomes. The models reveal that current score differential and team quality are the most important factors, while the timing of leads becomes increasingly crucial as games progress. The similar performance across different model types suggests that the relationships in the data are relatively straightforward and well-captured by various machine learning approaches.

This work provides a foundation for real-time win probability tracking and could be extended to incorporate more granular play-by-play data or player-level statistics in future iterations.
