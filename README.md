# Premier League Match Predictor

A machine learning-driven web application designed to predict the outcomes of English Premier League matches. This project utilizes a **Hybrid Model** (XGBoost and Random Forest) to provide accurate predictions based on team form and historical performance.

## Professional Hybrid Implementation
The core logic of this predictor relies on **Rolling Averages** (from the last 5 matches) rather than match-day stats. This approach prevents "Data Leakage" or "Cheating," ensuring the model only uses information that would actually be available *before* a kickoff.

### Key Features
*   **Predictive Modeling**: Combines the strengths of Random Forest and XGBoost for robust classification.
*   **Feature Engineering**: Implements rolling stats for goals, shots, corners, and cards to capture current "form".
*   **Schema Enforcement**: Built-in protection against **Inference-Training Skew**, ensuring the app only processes the 123 features the model was trained to recognize.
*   **Interactive UI**: Developed with Streamlit for a seamless user experience on Linux-based environments.

## Technical Stack
*   **Language**: Python 3.13
*   **Libraries**: `scikit-learn`, `pandas`, `numpy`, `xgboost`, `joblib`
*   **Framework**: Streamlit
*   **Environment**: Linux