# Premier League Match Predictor

A machine learning-driven web application designed to predict the outcomes of English Premier League matches. This project utilizes a **Hybrid Model** (XGBoost and Random Forest) to provide accurate predictions based on team form and historical performance.

## Professional Hybrid Implementation
The core logic of this predictor relies on **Rolling Averages** (from the last 5 matches) rather than match-day stats. This approach prevents "Data Leakage" or "Cheating," ensuring the model only uses information that would actually be available *before* a kickoff.
