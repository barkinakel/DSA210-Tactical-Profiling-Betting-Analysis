# Advanced Tactical Analysis & Betting Strategy
## DSA 210 Term Project - Fall 2025-2026

### Motivation
The primary motivation for this project is to test the **Efficient Market Hypothesis (EMH)** in the context of sports betting. EMH suggests that all publicly available information is already reflected in betting odds, making it impossible to systematically "beat" the market. 

This project challenges that notion by exploring whether a machine learning model—one that incorporates **tactical profiling** rather than just traditional win/loss records—can identify structural inefficiencies and valuable opportunities that the market has missed. It combines sports analytics with financial modeling to apply rigorous data science methodologies to a real-world problem.

### Data Sources
The project utilizes data from the following sources:
*   **FBref.com**: Used for detailed match and team statistics, including Expected Goals (xG), Possession, Touches in Attacking Penalty Area, and Defensive Actions.
*   **TotalCorner.com**: Used for historical corner kick odds to enable backtesting and value identification.

### Project Scope
While the initial research considered multiple leagues and betting markets, this project specifically narrows its focus to the **English Premier League** and the **Corner Kick Market**.
*   **Why Premier League?** It offers the highest availability of tactical data (e.g., "Touches in Attacking Third") required for deep profiling.
*   **Why Corner Market?** Unlike the highly efficient 1X2 (Win/Loss) market, the corner market is often less optimized by bookmakers, creating more opportunities for a specialized statistical model to find an edge.

### Methodology

The project follows a structured data science pipeline:

1.  **Data Collection & Preprocessing**:
    *   Aggregated match statistics from the English Premier League (2019-2024).
    *   Merged tactical metrics with historical betting odds.
    *   Performed cleaning and feature engineering (e.g., creating the "Box Siege" metric).

2.  **Exploratory Data Analysis (EDA)**:
    *   Conducted Paired T-Tests to quantify Home vs. Away performance bias.
    *   Validated the correlation between specific tactical metrics (like Box Touches) and Corner Kicks.

3.  **Tactical Profiling (Unsupervised Learning)**:
    *   Applied **K-Means Clustering** to categorize teams into distinct playing styles (e.g., *Elite Dominant*, *High Pressing*, *Deep Block*).
    *   Used Silhouette Analysis to determine the optimal number of clusters (K=6).

4.  **Predictive Modeling**:
    *   Developed a weighted 3-component prediction model combining:
        *   **Tactical Matchup History** (80% weight)
        *   **Season Averages** (15% weight)
        *   **Recent Form** (5% weight)
    *   Optimized weights using Grid Search to minimize Brier Score and MAE.

5.  **Betting Strategy & Optimization**:
    *   **Probabilistic Modeling**: Used the **Poisson Distribution** to calculate the "Fair Probability" of corner outcomes based on predicted totals.
    *   **Risk Management**: Introduced a **Safety Score** metric (Z-Score based) to filter bets where the edge exceeds historical variance.
    *   **Staking Strategy**: Simulated a staking plan to optimize capital allocation (Edge Power, Confidence Threshold, Volatility Penalty).

### Key Findings
*   **Tactical Correlations**: Specific matchups, such as a "Box Siege" team playing against a "Deep Block" team, produce a statistically significant surplus of corners compared to the league average.
*   **Market Inefficiency**: The model identified that bookmakers often underprice these specific tactical mismatches, creating a "Value Bet" opportunity.
*   **Profitable Thresholds**: Backtesting revealed that a **Safety Score > 0.22** for "Over" bets yielded a profitable win rate (>52.7%) with a robust sample size.

### Installation & Usage

1.  **Clone the Repository**:
    ```bash
    git clone <your-repo-url>
    cd <your-repo-name>
    ```
2.  **Install Dependencies**:
    ```bash
    pip install -r requirements.txt
    ``
 Ensure the `premier_league_metrics.csv` file is located in the `Data/` directory.

4.  **Run the Analysis**:
    *   Open `Tactical_analysis_and_strategy.ipynb` in Jupyter Notebook or VS Code.

### Limitations & Future Work
*   **Game State Bias**: The current model uses aggregate match stats and does not account for game state (e.g., a team stopping attacks after leading 3-0).
*   **Data Quality**: Detailed tactical data is less reliable for lower-tier leagues, limiting immediate expansion.
*   **Future Expansion**: Plans include testing the framework on other major European leagues (La Liga, Bundesliga) and incorporating "Corner Handicap" markets once reliable historical data is sourced.
*   **Market Diversification**: Expanding the model to cover not just Corner markets, but also general markets such as **Over/Under** (e.g., Total Goals) and to broaden the strategy's scope.

  ### Academic Integrity
This project is submitted as part of the DSA 210 course requirements.
*   **AI Usage**: Generative AI tools were utilized extensively throughout the entire development process. This includes assistance with writing data scraping scripts, implementing complex feature engineering logic, debugging code, optimizing model parameters, and drafting technical documentation. AI acted as a co-pilot to accelerate the implementation of the project pipeline.
*   **Citations**: Data sources (FBref, TotalCorner) and external libraries are properly credited.
