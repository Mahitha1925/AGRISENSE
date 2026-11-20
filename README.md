# 🌾 AGRISENSE
### Smart Agriculture Monitoring and Management System

AGRISENSE is a smart farming platform designed to support farmers with data-driven agricultural insights. It combines machine learning, weather information, crop prediction, market price forecasting, and farming-related tools in one application.

## 🚀 Key Features

- **Crop Prediction:** Predict suitable crops using soil and climate inputs with Random Forest and Decision Tree models.
- **Weather Analysis:** View location-based current weather information, a 7-day forecast, weather alerts, and farming advisories.
- **Market Price Forecasting:** Forecast crop prices using ARIMA and LSTM models, with selectable forecast periods.
- **Model Comparison:** Compare crop prediction and price forecasting model metrics.
- **Disease Diagnosis:** Explore crop disease information, symptom matching, and treatment and prevention guidance.
- **Farmer Profile:** Maintain farmer details for personalized farming support.
- **Financial Tools:** Access loan EMI calculations, fertilizer optimization, profit estimation, and cost analysis.
- **Government Schemes:** Find farming-related scheme information.
- **AI Farming Assistant:** Access an in-app assistant for farming-related guidance.

## 🛠️ Technologies Used

| Area | Technologies |
|---|---|
| Programming language | Python |
| Dashboard | Streamlit |
| Backend API | FastAPI, Uvicorn |
| Data processing | Pandas, NumPy |
| Machine learning | Scikit-learn |
| Crop prediction | Random Forest, Decision Tree |
| Time-series forecasting | ARIMA, TensorFlow, Keras, LSTM |
| Data visualization | Plotly, Matplotlib, Seaborn |
| API integration | Requests, aiohttp |
| Model storage | Pickle, Joblib |

## 📁 Project Structure

```text
AGRISENSE/
│
├── app.py
├── main.py
├── price_data.py
├── requirements.txt
├── .gitignore
│
├── data/
│   ├── SoilCrops_2000.csv
│   ├── historical_prices.csv
│   └── trained_models/
│       ├── crop_models.pkl
│       └── price_models/
│           ├── arima_model.pkl
│           ├── lstm_model.h5
│           ├── lstm_scaler.pkl
│           └── metrics.pkl
│
├── models/
│   ├── crop_predictor.py
│   ├── model_comparison.py
│   └── price_forecaster.py
│
└── utils/
    ├── preprocessing.py
    └── weather.py
```

## ⚙️ Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/Mahitha1925/AGRISENSE.git
cd AGRISENSE
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

### 3. Activate the environment

**Windows:**

```bash
venv\Scripts\activate
```

### 4. Install dependencies

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

## ▶️ Run the Application

### Streamlit Dashboard

Run:

```bash
streamlit run app.py
```

The application will open in your browser. If it does not open automatically, visit:

```text
http://localhost:8501
```

### FastAPI Backend (Optional)

Open another terminal, activate the virtual environment, and run:

```bash
uvicorn main:app --reload
```

Open the API documentation at:

```text
http://127.0.0.1:8000/docs
```

## 🌦️ Weather API Configuration

The weather module supports OpenWeatherMap integration.

To enable live weather data:

1. Obtain an API key from [OpenWeatherMap](https://openweathermap.org/api).
2. Create a `.env` file in the project root.
3. Add:

```env
OPENWEATHER_API_KEY=your_api_key_here
```

Keep `.env` private. It is excluded through `.gitignore`.

**Note:** The weather module includes fallback behavior that generates synthetic weather data when an API key is unavailable or a request fails.

## 📊 Data and Model Notes

- Crop prediction uses the soil and crop dataset in `data/SoilCrops_2000.csv`.
- Crop models include Random Forest and Decision Tree.
- Price forecasting includes ARIMA and LSTM models.
- The preprocessing module generates synthetic historical price data for forecasting workflows. Forecasts should therefore be treated as model outputs, not guaranteed market prices.

*AGRISENSE — Bringing data-driven insights to smarter farming.*
