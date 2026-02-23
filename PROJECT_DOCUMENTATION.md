# 🌾 AI-Based Crop Yield Prediction and Analysis System
## Real-Time Data Integration with Machine Learning

---

## 📋 Project Overview

**Student:** Vinotha S  
**Registration:** 7376242CB158  
**Department:** Computer Science and Business Systems (CSBS)  
**Institution:** Bannari Amman Institute of Technology  
**Domain:** Artificial Intelligence / Machine Learning  
**Application:** Smart Agriculture

### SDG Alignment
- **SDG 2:** Zero Hunger
- **SDG 12:** Responsible Consumption and Production

---

## 🎯 Project Objectives

1. **Predict crop yields** using Machine Learning based on:
   - Soil nutrient levels (N, P, K, pH)
   - Real-time weather data (temperature, rainfall, humidity)
   - Historical patterns and trends

2. **Provide economic analysis** including:
   - Expected revenue calculations
   - Cost-benefit analysis
   - Profit margin predictions

3. **Generate actionable recommendations** for:
   - Soil nutrient management
   - Irrigation planning
   - Crop selection optimization

4. **Support farmers** in Gopalapuram and Salem district with data-driven decision making

---

## 🏗️ System Architecture

### Components

1. **Machine Learning Module** (`crop_yield_prediction.py`)
   - Random Forest Regressor model
   - Feature importance analysis
   - Confidence interval calculation

2. **Real-Time Weather Integration**
   - Open-Meteo API integration
   - 7-day weather forecast
   - Location-based data retrieval

3. **Economic Analysis Engine**
   - Market price database
   - Revenue/cost calculations
   - Profitability analysis

4. **Web Dashboard** (`yield_prediction_dashboard.html`)
   - Interactive user interface
   - Real-time predictions
   - Crop comparison tool

---

## 🔬 Technical Implementation

### Machine Learning Model

**Algorithm:** Random Forest Regressor

**Features (Input Parameters):**
- Nitrogen (N): 0-140 kg/ha
- Phosphorus (P): 5-145 kg/ha
- Potassium (K): 5-205 kg/ha
- Soil pH: 4.5-9.0
- Temperature: 15-40°C
- Humidity: 20-100%
- Rainfall: 20-300 mm
- Cultivated Area: hectares
- Crop Type: encoded (9 categories)

**Target Variable:**
- Yield in kg/hectare

**Model Performance Metrics:**
- R² Score: ~0.27 (on synthetic data)
- RMSE: ~861 kg/hectare
- MAE: ~704 kg/hectare

*Note: Performance will improve significantly with real historical data*

### Supported Crops

1. Rice (धान)
2. Wheat (गेहूं)
3. Cotton (कपास)
4. Sugarcane (गन्ना)
5. Groundnut (मूंगफली)
6. Maize (मक्का)
7. Pulses (दाल)
8. Vegetables (सब्जियां)
9. Flowers (फूल)

### Real-Time Weather API

**Provider:** Open-Meteo (Free, No API Key Required)

**Data Retrieved:**
- Maximum/Minimum temperatures
- Precipitation (rainfall)
- Relative humidity
- 7-day forecast

**Supported Locations:**
- Gopalapuram
- Salem
- Chennai
- Coimbatore
- Madurai
- Tiruchirappalli
- And more...

---

## 💻 Installation & Setup

### Prerequisites

```bash
Python 3.8+
pip (Python package manager)
Internet connection (for weather API)
```

### Required Libraries

```bash
pip install numpy pandas scikit-learn requests
```

### Quick Start

1. **Clone/Download the project files:**
   - `crop_yield_prediction.py`
   - `yield_prediction_dashboard.html`

2. **Run the Python system:**
```bash
python3 crop_yield_prediction.py
```

3. **Open the web dashboard:**
   - Open `yield_prediction_dashboard.html` in a web browser
   - Chrome, Firefox, or Safari recommended

---

## 📊 Usage Guide

### Using the Python System

```python
from crop_yield_prediction import CropYieldPredictor, RealTimeWeatherAPI

# Initialize
predictor = CropYieldPredictor()
weather_api = RealTimeWeatherAPI()

# Train model (one-time)
predictor.train_model()

# Get weather data
lat, lon = 11.75, 78.10  # Gopalapuram coordinates
weather = weather_api.get_weather_data(lat, lon)

# Define soil parameters
soil = {
    'N': 75,
    'P': 65,
    'K': 85,
    'pH': 6.8
}

# Predict yield
result = predictor.predict_yield(
    soil_params=soil,
    weather_params=weather,
    crop_type='groundnut',
    area_hectares=2.5
)

print(f"Predicted Yield: {result['predicted_yield_per_hectare']} kg/ha")
print(f"Total Yield: {result['total_predicted_yield_tonnes']} tonnes")
```

### Using the Web Dashboard

1. **Enter Soil Parameters:**
   - Nitrogen, Phosphorus, Potassium levels
   - pH value

2. **Select Crop and Area:**
   - Choose crop from dropdown
   - Enter cultivated area in hectares
   - Select location

3. **Fetch Weather & Predict:**
   - Click "Fetch Weather & Predict Yield"
   - System retrieves real-time weather
   - ML model generates prediction

4. **View Results:**
   - Yield prediction with confidence interval
   - Economic analysis (revenue, profit, margin)
   - Agronomic recommendations

5. **Compare Crops:**
   - Click "Compare All Crops"
   - See side-by-side comparison
   - Identify most profitable option

---

## 📈 Sample Outputs

### Groundnut Prediction (2.5 hectares)

**Input Conditions:**
- N: 75 kg/ha, P: 65 kg/ha, K: 85 kg/ha, pH: 6.8
- Temperature: 28.5°C, Rainfall: 75mm, Humidity: 70%

**Prediction:**
- Yield: 2,412 kg/hectare
- Total: 6.03 tonnes
- Confidence: 2,171 - 2,653 kg/ha

**Economics:**
- Revenue: ₹3,31,667
- Cost: ₹62,500
- Profit: ₹2,69,167
- Margin: 81.16%

### Feature Importance Analysis

| Feature | Importance |
|---------|-----------|
| Nitrogen (N) | 17.2% |
| Phosphorus (P) | 15.0% |
| Potassium (K) | 14.4% |
| Rainfall | 13.5% |
| pH | 10.3% |
| Temperature | 9.0% |
| Humidity | 8.6% |
| Area | 8.2% |
| Crop Type | 3.7% |

---

## 🔧 Customization Options

### Adding New Crops

```python
# In crop_yield_prediction.py
self.crop_encodings = {
    'rice': 0,
    'wheat': 1,
    # Add new crop
    'mustard': 10
}

# In YieldAnalyzer
self.crop_market_prices = {
    'rice': 2500,
    # Add price
    'mustard': 4500
}
```

### Adding New Locations

```python
# In RealTimeWeatherAPI
locations = {
    'salem': (11.6643, 78.1460),
    # Add new location
    'erode': (11.3410, 77.7172)
}
```

### Adjusting Cost Estimates

```python
# In YieldAnalyzer.calculate_economics()
estimated_cost = area * 25000  # Change multiplier
```

---

## 🎓 Educational Value

### Learning Outcomes

Students will learn:

1. **Machine Learning:**
   - Regression algorithms
   - Feature engineering
   - Model evaluation
   - Hyperparameter tuning

2. **API Integration:**
   - REST API calls
   - JSON data parsing
   - Error handling
   - Rate limiting

3. **Data Science:**
   - Data preprocessing
   - Statistical analysis
   - Confidence intervals
   - Feature importance

4. **Agricultural Domain:**
   - Soil science
   - Crop requirements
   - Weather impact
   - Economic analysis

5. **Full-Stack Development:**
   - Backend (Python)
   - Frontend (HTML/CSS/JS)
   - Real-time data flow
   - User experience design

---

## 🌱 Field Study Integration

### Based on Actual Farmer Surveys

**Location:** Gopalapuram, Salem District  
**Farmers Surveyed:** 6  
**Date:** January 10-18, 2026

**Key Findings:**
1. Farmers rely on experience, not data
2. Wrong crop selection causes financial loss
3. Smartphone penetration: High
4. Internet access: Moderate to Good
5. Willingness to adopt: Strong (if simple and low-cost)

### Addressing Real Problems

| Problem | Solution |
|---------|----------|
| Experience-based selection | Data-driven ML predictions |
| No soil testing | NPK input parameters |
| Climate uncertainty | Real-time weather integration |
| Financial risk | Economic analysis tool |
| Technical literacy | Simple web interface |

---

## 📱 Mobile Optimization

The web dashboard is fully responsive:
- ✅ Works on smartphones
- ✅ Touch-friendly interface
- ✅ Offline capability (after initial load)
- ✅ Low data usage
- ✅ Regional language support (expandable)

---

## 🔮 Future Enhancements

### Phase 2 (Short Term)

1. **Database Integration:**
   - Store historical predictions
   - Track actual vs predicted yields
   - Continuous model improvement

2. **SMS/WhatsApp Notifications:**
   - Weather alerts
   - Price updates
   - Harvest timing reminders

3. **Regional Language Support:**
   - Tamil interface
   - Voice input/output
   - Text-to-speech recommendations

4. **Soil Testing Integration:**
   - Upload soil test reports
   - Auto-populate nutrient values
   - Testing lab partnerships

### Phase 3 (Long Term)

1. **IoT Sensor Integration:**
   - Real-time soil moisture
   - Automated pH monitoring
   - Weather station data

2. **Satellite Imagery:**
   - Crop health monitoring
   - Yield estimation from space
   - Pest/disease detection

3. **Market Integration:**
   - Live commodity prices
   - Buyer-seller matching
   - Contract farming support

4. **Government Scheme Integration:**
   - Subsidy information
   - Insurance claim automation
   - Agricultural credit linking

---

## 🤝 Social Impact

### Direct Benefits to Farmers

1. **Increased Income:**
   - Better crop selection → Higher yields
   - Reduced input waste → Lower costs
   - Market price awareness → Better selling

2. **Risk Reduction:**
   - Weather-based planning
   - Soil-specific recommendations
   - Economic forecasting

3. **Empowerment:**
   - Data-driven decision making
   - Reduced dependency on middlemen
   - Financial planning capability

### Community Impact

- **Food Security:** Improved agricultural productivity
- **Employment:** Supporting agricultural laborers
- **Sustainability:** Optimized resource usage
- **Education:** Digital literacy in rural areas

---

## 📞 Support & Contact

**Developer:** Vinotha S  
**Email:** vinothas.cb24@bitsathy.ac.in  
**Institution:** Bannari Amman Institute of Technology

**For Technical Support:**
- Check documentation
- Review sample code
- Contact via email

**For Farmer Support:**
- Visit local agricultural office
- Contact: Agricultural Department, Salem
- Website: tn.gov.in

---

## 📜 License & Credits

### Open Source Libraries
- **NumPy:** Numerical computing
- **Pandas:** Data manipulation
- **Scikit-learn:** Machine learning
- **Requests:** HTTP library

### APIs
- **Open-Meteo:** Weather data (Free tier)

### Acknowledgments
- Field study participants (6 farmers)
- Bannari Amman Institute of Technology
- Institutions Innovation Council

---

## 🔒 Data Privacy & Ethics

1. **Farmer Data:**
   - No personal data stored
   - Anonymous usage statistics only
   - GDPR/privacy compliant

2. **Predictions:**
   - Provided as guidance, not guarantee
   - Farmers make final decisions
   - No liability for crop failure

3. **Transparency:**
   - Model limitations disclosed
   - Data sources cited
   - Accuracy metrics shown

---

## 📊 Performance Benchmarks

### System Performance

- **Prediction Time:** < 1 second
- **Weather API Call:** 2-5 seconds
- **Model Training:** 10-15 seconds
- **Web Dashboard Load:** < 2 seconds

### Accuracy Targets

- **Training Data (Synthetic):** R² = 0.27
- **Real Data (Expected):** R² > 0.70
- **Economic Predictions:** ±15% margin

*Note: Accuracy improves with real historical data collection*

---

## 🎯 Success Metrics

### Technical Metrics
- ✅ Model deployed and functional
- ✅ Real-time weather integration working
- ✅ Web dashboard responsive
- ✅ All crops supported

### Social Metrics
- ✅ 6 farmers surveyed
- ✅ High willingness to adopt (100%)
- ✅ Addresses key pain points
- ✅ Low-cost, accessible solution

### Impact Metrics (Target)
- Increase yield prediction accuracy: 70%+
- Reduce crop selection errors: 50%+
- Improve farmer income: 20%+
- Reach 100+ farmers in Year 1

---

## 📚 References

1. **Agricultural Data:**
   - Tamil Nadu Agricultural Department
   - Indian Council of Agricultural Research (ICAR)

2. **Machine Learning:**
   - Scikit-learn Documentation
   - Random Forest Algorithm Papers

3. **Weather Data:**
   - Open-Meteo API Documentation
   - Indian Meteorological Department

4. **Market Prices:**
   - Agricultural Market Intelligence
   - Minimum Support Price (MSP) Data

---

## 🚀 Deployment Checklist

- [x] Python system tested
- [x] Web dashboard functional
- [x] Real-time weather working
- [x] Documentation complete
- [ ] Real farmer data collection
- [ ] Model retraining with real data
- [ ] Regional language translation
- [ ] Mobile app development
- [ ] Field deployment in Gopalapuram
- [ ] Feedback collection system

---

## ⚠️ Important Notes

1. **This is a prototype** developed for educational purposes
2. **Current model uses synthetic data** - needs real data for production
3. **Predictions are guidance only** - farmers should consult agricultural experts
4. **Weather API requires internet** - offline mode planned for future
5. **Free tier limits:** 10,000 API calls/day (sufficient for pilot)

---

## 🎓 Conclusion

This AI-based Crop Yield Prediction System successfully:

✅ Integrates real-time weather data  
✅ Uses Machine Learning for predictions  
✅ Provides economic analysis  
✅ Offers actionable recommendations  
✅ Addresses real farmer problems  
✅ Aligns with UN SDGs  
✅ Scalable and sustainable  

The system is ready for pilot deployment in Gopalapuram and can be scaled across Tamil Nadu with proper data collection and farmer training.

---

**Project Status:** ✅ PHASE 1 COMPLETE  
**Next Phase:** Real data collection & model refinement  
**Target Deployment:** June 2026 (Kharif season)

---

*Developed with 💚 for farmers of Tamil Nadu*
*By Vinotha S, CSBS, BIT*
