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

## The Data Pipeline & Challenges
As an engineering student, I focused on making this model technically sound for real-world deployment:

*   **Handling Feature Drift**: The app dynamically maps user-friendly labels (like "Away Shots") to technical rolling features (like `AwayShots_roll`) used during training.
*   **Schema Validation**: The inference engine uses a "Clean Room" DataFrame approach to filter out any "unseen" features, preventing runtime crashes caused by shape mismatches.
*   **Anti-Leakage Logic**: By strictly enforcing a rolling-average input, the model is forced to predict based on momentum rather than current-game statistics.

### Future Roadmap
- [ ] Integration with live APIs (e.g., FBRef) for automatic "Form" fetching.
- [ ] Support for other major European leagues (La Liga, Serie A).
- [ ] Deployment to Streamlit Cloud for public access.

---

## 📋 Installation & Usage

1.  **Clone the repository**:
2. **Install dependencies**:
    ```bash
    pip install streamlit pandas joblib scikit-learn xgboost
    ```
3.  **Run the App**:
    ```bash
    streamlit run app.py
    ```
---
## Conclusion

The development of the Premier League Match Predictor successfully demonstrates the transition from a localized data science script to a robust, deployment-ready web application. Through this project, several critical engineering and machine learning milestones were achieve:

### 1. Model Architecture & Non-Linear Complexity
By moving beyond basic linear regression to a **Hybrid Model** (XGBoost and Random Forest), the system gained the ability to capture complex, non-linear relationships within football match data. This ensures that the model accounts for the volatile nature of sports statistics where a single metric rarely determines the outcome.

### 2. Schema Rigidity & Inference Integrity
A significant technical challenge addressed was **Inference-Training Skew**. The implementation of a "Clean Room" DataFrame and strict **Schema Enforcement** ensured that the inference engine remained perfectly aligned with the model's 123 original training features. This prevented runtime crashes and ensured that the data processed by the `StandardScaler` was consistent with the training distribution.

### 3. Ethical Machine Learning: Anti-Leakage Design
The project strictly adheres to professional standards by using **Rolling Averages** rather than current match-day stats. This design prevents "Data Leakage" (cheating), forcing the model to make predictions based solely on the historical momentum and form of the teams involved.

### 4. Scalable Infrastructure
Developed within a Linux environment on a Lenovo IdeaPad 5, the project serves as a scalable foundation for future enhancements, such as automated live-API data ingestion and multi-league support.