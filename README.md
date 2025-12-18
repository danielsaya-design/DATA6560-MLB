# DATA6560-MLB
Predicting MLB Team Records Using Historical Data

This project evaluates whether historical, team-level MLB performance metrics can be used to accurately predict regular-season win totals. Using data from Baseball Reference and FanGraphs, regression and machine learning models are trained on past seasons, validated on the completed 2025 season, and then applied to generate projections for the upcoming season. Project success was defined as achieving predictions within approximately ±5 wins per team, indicating practical usefulness rather than perfect accuracy 



Problem & Stakeholders

Following the conclusion of the 2025 MLB season, this project investigates the question: Can a data-driven model accurately predict MLB team win totals using historical team-level statistics?

Accurate win projections provide value to several stakeholders:

MLB front offices, by highlighting strengths, weaknesses, and areas for improvement

Fans and analysts, by setting informed expectations entering a season

Sports bettors, by offering insight into projected team performance

Dataset Overview

Each row in the dataset represents one MLB team in one season. The dataset spans the 2010–2025 seasons, with the 2020 COVID-shortened season excluded.

Primary data sources: Baseball Reference & FanGraphs

The core data consists of two team-season datasets: Batting statistics (480 rows × 67 columns) & Pitching statistics (480 rows × 91 columns)

These datasets were merged on Season and Team to form a single master dataset containing advanced offensive and pitching metrics such as WAR, OPS+, ERA, WHIP, FIP, run rates, and situational performance measures. All 30 MLB teams are represented in every season, with no missing values or duplicate records 

Method & Approach

The analysis progressed through several structured checkpoints:

Data Cleaning & Preparation (CP4):
Batting and pitching datasets were validated, merged, and filtered to remove the 2020 season. Derived features such as total WAR and efficiency-based metrics were created to support modeling.

Exploratory Data Analysis (CP5):
Distributions and relationships between key variables and team wins were examined. Teams typically clustered between 70–95 wins, with relatively few extreme outliers. WAR emerged as the strongest single predictor, showing a very strong positive relationship with wins and reflecting combined offensive and pitching performance 

Model Development & Evaluation (CP6–CP7):
Initial modeling approaches performed poorly, with early models producing an MAE of 17.5 wins, well off our target. To address this, the modeling approach was revised, replacing a random forest model with a gradient boosting model better suited for structured numeric data.

Final Model & Validation (CP7):
The gradient boosting model substantially improved performance, achieving a mean absolute error (MAE) of 7.31 wins on the 2025 validation season. Feature importance analysis showed that pitching-related metrics including OPS+ allowed, pitching WAR, WHIP, and ERA were among the most influential predictors, alongside offensive OPS. This indicates that run prevention is more stable and predictive year-over-year than raw offensive output 

.

Key Results

The final model achieved an MAE of 7.31 wins on the 2025 validation season.

Pitching metrics consistently dominated feature importance rankings.

While the model did not meet the original ±5 win target, it demonstrated meaningful predictive power and substantial improvement over earlier approaches.

Final validation and projection visualizations are stored in the /figures folder.

How to View or Reproduce the Analysis

Cleaned dataset:
Available in /data

Reports:
PDF submissions for Checkpoints 1 through 8 are stored in the /reports folder and document each stage of the project.

Code:
Jupyter notebooks used for data preparation, EDA, modeling, and evaluation are located in /figures and can be run sequentially to reproduce the analysis.

Any required software packages or assumptions are noted within the notebooks.

Repository Map

/data – Raw and cleaned datasets and the data dictionary

/figures – Final charts and visualizations used in analysis

/reports – PDF reports for Checkpoints 1–8


The model operates at the team-season level and does not account for in-season injuries, roster turnover, or schedule effects.

External factors such as division strength and mid-season trades are not explicitly modeled.

Future work could incorporate player-level projections, preseason roster data, or probabilistic win distributions rather than single-point estimates.


Contributors:
Daniel Saya
Matthew Demarco
 
Data sourced from Baseball reference and Fangraphs
