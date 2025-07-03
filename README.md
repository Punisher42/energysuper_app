# 🏠 Smart Home Appliance Energy Predictor

A full-stack machine learning application for predicting smart home appliance energy usage. Built with **FastAPI** (backend) and **Streamlit** (frontend), it enables live energy forecasting, historical trend visualization, and insight into feature importance using a trained **XGBoost** model.

---

## ✨ Features

- 🔮 **Live Prediction** – Estimate appliance energy usage using weather, time, and activity inputs.
- 📈 **Trend Analysis** – Upload a `.csv` to visualize past appliance usage over time.
- 🔍 **Model Explainability** – Explore the most important features influencing the energy model.

---

## 📁 Project Structure

```
.
├── app2.py                        # Streamlit dashboard (frontend)
├── main.py                        # FastAPI server (backend API)
├── requirements.txt               # Python dependencies
├── xgboost_appliance_model.pkl    # Pre-trained XGBoost model
├── feature_importance.png         # Visualization of top features
├── sample_appliance_usage.csv     # Sample CSV for usage trend testing
├── energydata_complete.csv        # Full dataset (optional)
├── Appliances_Energy_Prediction.ipynb  # Notebook used during model training
```

---

## ⚙️ Setup Instructions

Follow these steps to get the app running locally:

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/energy-app.git
cd energy-app
```

### 2. (Optional) Create a Virtual Environment

```bash
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate
```

### 3. Install Python Dependencies

```bash
pip install -r requirements.txt
```

---

## 🚀 Usage Guidelines

### Step 1: Start the FastAPI Backend Server

This will load the trained model and expose an API for predictions.

```bash
uvicorn main:app --reload
```

✅ **Runs at:** `http://127.0.0.1:8000`  
🔍 **Try the API Docs:** `http://127.0.0.1:8000/docs`

---

### Step 2: Launch the Streamlit Frontend Dashboard

This is the interactive user interface for predictions and analysis.

```bash
streamlit run app2.py
```

📍 Open in browser: `http://localhost:8501`

---

## 🧠 How to Use the Dashboard

### 📊 Tab 1: Predict Usage

- **Inputs**: Hour, day, outdoor temperature, humidity, visibility, dew point, and activity level.
- **Output**: Predicted energy usage (in watt-hours).
- Uses your inputs to make a real-time prediction by calling the backend API.

### 📈 Tab 2: Upload CSV Trend

- Upload a `.csv` file with:
  - `datetime`: timestamp
  - `Appliances`: corresponding energy usage
- The dashboard plots appliance usage over time.

📌 **Example CSV**:

```csv
datetime,Appliances
2016-01-11 17:00:00,60
2016-01-11 17:10:00,65
```

### 🔍 Tab 3: Feature Importance

- Visualizes the most important features contributing to energy predictions using XGBoost.
- Explains each feature in simple language for user understanding.

---

## 🧾 Model Input Features

| Feature             | Description                          |
|---------------------|--------------------------------------|
| T_out               | Outdoor temperature (°C)             |
| RH_out              | Outdoor humidity (%)                 |
| Visibility          | Outdoor visibility (km)              |
| Tdewpoint           | Dew point temperature (°C)           |
| hour                | Hour of the day (0–23)               |
| day_of_week         | Day index (0=Mon to 6=Sun)           |
| is_weekend          | 1 if weekend, 0 otherwise            |
| Appliances_lag1     | Energy usage 1 hour ago              |
| Appliances_lag24    | Energy usage 24 hours ago            |
| Appliances_roll3    | Avg. usage in last 3 hours           |
| Appliances_roll6    | Avg. usage in last 6 hours           |

---

## 📷 Screenshots (Optional)

> _Add Streamlit screenshots of live predictions and trend plots for visual reference._

---

## 📜 License

This project is licensed under the **MIT License**. See `LICENSE` for details.

---

## 👩‍💻 Author

**Aditya Kumar Roy**  
_Enabling smarter living through AI & data_
