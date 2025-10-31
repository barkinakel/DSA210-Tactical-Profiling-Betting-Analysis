# DSA210-Team-Profile-Market-Analysis
# Motivation
My motivation for this project is to test "Efficient Market Hypothesis" which states that all publicly available information is already fully and accurately reflected in the betting odds, making it impossible to systematically "beat the market. This project aims to explore whether a machine learning model, which considers underlying factors like playing styles that go beyond traditional statistics, systematically identify valuable opportunities that the market has missed. This project combines my interest in football with market analysis to apply data science methodologies to a practical, real world problem.
# Data Source
The project will make use of publicly available datasets:  

- **football-data.co.uk** - Contains detailed match-level statistics (shots, corners, cards, etc.) for past seasons in major European leagues.  
- **FBref.com** - Provides detailed match and team statistics such as expected goals (xG), possession, and pressing metrics.  
- **oddsPortal.com** - Contains historical bookmaker odds across multiple markets, allowing comparison between model's and market-implied odds to identify potential value bets.
# Data Analysis
I plan to analyze seasonal team statistics and group teams that have similar statistical profiles. Next, I will train a model based on these profiles to predict match outcomes. Finally, I will compare the model's predictions against the market's odds and conduct a backtesting process to see if a profitable strategy exists.
