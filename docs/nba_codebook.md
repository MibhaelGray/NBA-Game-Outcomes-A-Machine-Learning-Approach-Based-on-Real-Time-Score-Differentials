# NBA Game Dataset Codebook

## Dataset Overview
This dataset tracks NBA games from the 2022-23 season by taking snapshots every 30 seconds during gameplay. I collected this data to analyze how win probability changes throughout games and build predictive models for game outcomes.

## Variables

**Team Info:**
- `HOME_TEAM` - Home team name (e.g., "Boston Celtics")
- `AWAY_TEAM` - Away team name (e.g., "Philadelphia 76ers")

**Game Time:**
- `seconds_elapsed` - Seconds since game started (0 = tipoff, 2880 = end of regulation)
- `PERIOD` - Quarter number (1-4 for regular time)

**Current Score:**
- `HOME_SCORE` - Home team's current score
- `AWAY_SCORE` - Away team's current score  
- `SCORE_DIFF` - Point differential (home minus away score)
- `IS_HOME_LEADING` - 1 if home team ahead, 0 if tied or behind

**Team Strength:**
- `HOME_TEAM_WIN_PCT` - Home team's season win percentage going into this game
- `AWAY_TEAM_WIN_PCT` - Away team's season win percentage going into this game

**Game Result:**
- `HOME_TEAM_WON` - Final outcome: 1 if home team won, 0 if lost

**My Custom Variable:**
- `MOMENTUM` - How much the score differential changed in the last 2 minutes

## Data Notes

I removed all overtime games because there weren't enough games that went to overtime for it to be useful to study or train on. The final dataset has about 63,000 observations from roughly 1,200 games.

Each game has around 96 rows since I'm taking snapshots every 30 seconds. The `HOME_TEAM_WON` variable is the same for all rows from the same game since it's just the final result.
