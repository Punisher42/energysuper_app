## 🏠 Smart Home Appliance Energy Predictor

This project is a full-stack AI-powered application that predicts energy consumption of home appliances based on weather and time-related features. Built with **Streamlit** (frontend) and **FastAPI** (backend), it offers real-time prediction, trend analysis, and model explainability using feature importance.

---

## 🚀 Features

- 🔮 **Live Prediction**: Predict appliance energy usage based on live inputs like time, temperature, humidity, and user activity.
- 📈 **CSV Trend Analysis**: Upload past usage data to visualize consumption trends over time.
- 🔍 **Feature Importance**: Understand which features most influence the energy consumption model (XGBoost).

---

## 📦 File Structure

```bash
.
├── app2.py                       # Streamlit frontend
├── main.py                       # FastAPI backend (model API)
├── xgboost_appliance_model.pkl   # Trained XGBoost model
├── feature_importance.png        # Visualization of top predictive features
├── energydata_complete.csv       # Original dataset
├── sample_appliance_usage.csv    # Example CSV for testing trend visualization
├── requirements.txt              # Dependencies
└── Appliances_Energy_Prediction.ipynb  # Jupyter notebook for exploration
