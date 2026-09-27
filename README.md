# AgroFarm
This project implements a machine learning-based solution that processes and analyzes satellite imagery (Sentinel-2) to predict agricultural yields. The system incorporates vegetation indices, weather data, and historical yield information to provide accurate yield forecasts and crop health monitoring, enabling decision-making in agriculture

# Table of Content:
Introduction
Overview of AgroFarm
Objectives

#Data Sources

Sentinel-2 Satellite Imagery
Vegetation Indices
Weather Data
Historical Yield Data

# Technology Stack:
   • Google colab 
   • Google earth engine 
   • ML and DL
## ✨ Features

- **🌱 Personalized Crop Advisory**
  - AI-driven recommendations for planting, irrigation, fertilization, and pest control.
  - Tailored advice based on local conditions and crop types.
  - Sustainable farming practice suggestions.

- **☁️ Real-Time Weather & Climate Updates**
  - Hyperlocal weather forecasts.
  - Climate alerts for extreme weather events.
  - Seasonal climate predictions.

- **📊 IoT & Remote Sensing Dashboard**
  - Monitor soil moisture, temperature, and nutrient levels through IoT sensors.
  - Access satellite and drone imagery for crop health analysis.
  - Visual analytics of farm conditions.

- **💧 Resource Management Tools**
  - Calculate optimal water usage.
  - Determine fertilizer requirements.
  - Recommend energy-efficient practices.

- **🤖 Predictive AI Features**
  - Optimal irrigation timing recommendations.
  - Best sowing windows calculation.
  - Precise pesticide application guidance.
  - Crop suitability recommendations.
  - Estimated yield predictions.

- **📝 Farm Management System**
  - Task management.
  - Inventory tracking.
  - Crop lifecycle management.
  - Financial record keeping.

- **💬 24/7 AI Assistant**
  - Instant answers to farming questions.
  - Powered by Google's Gemini API.
  - Continuous learning and improvement.

---

## 🏗️ System Architecture

                         ┌──────────────┐
                         │    Users     │
                         └──────┬───────┘
                                │
                         Auth Request
                                │
                                ▼
                         ┌──────────────┐
                         │ Auth System  │
                         └──────┬───────┘
                                │
                         Auth Response
                                │
                                ▼
                    ┌──────────────────────┐
                    │  Authenticated Users │
                    └──────────┬───────────┘
                               │
                               ▼
                         ┌──────────────┐
                         │  Dashboard   │
                         └──────┬───────┘
                                │
             ┌──────────────────┼──────────────────┐
             ▼                  ▼                  ▼
   ┌─────────────────┐ ┌────────────────┐ ┌─────────────────┐
   │ Farm Area       │ │   Farm Data    │ │  AI Assistant   │
   │ Selection       │ │                │ │                 │
   └────────┬────────┘ └───────┬────────┘ └─────────────────┘
            │                  │
            └──────────┬───────┘
                       ▼
                ┌──────────────┐
                │   FastAPI    │
                └──────┬───────┘
                       │
                  POST Request
                       │
                       ▼
          ┌─────────────────────────────┐
          │        ML Models            │
          ├─────────────────────────────┤
          │ Crop Health Monitoring      │
          │ Yield Prediction            │
          │ Water Stress Region         │
          │ Soil Condition               │
          └──────────────┬──────────────┘
                         │
                    Predictions
                         │
                         ▼
                    ┌──────────┐
                    │ Response │
                    └──────────┘


External Data Sources
────────────────────────────────────────────

┌──────────────┐       ┌──────────────┐
│ Google Maps  │       │  Open Meteo  │
└──────┬───────┘       └──────┬───────┘
       │                      │
       ▼                      ▼
 Farm Location            Weather Data

 ML / Data Architecture : 
 Google Earth Engine
        │
        ▼
Harmonized Sentinel-2 MSI
        │
        ▼
Satellite Images
        │
        ▼
Vegetation Index Calculation
        │
        ├──────────────► NDVI
        │
        └──────────────► NDWI
        │
        ▼
Time Series Data
        │
        ▼
Mean Value Extracted
        │
        ▼
Time Series Added
        │
        ▼
Interpolated Dataset
        │
        ▼
┌─────────────────────────┐
│       LSTM Model        │
│                         │
│ Activation: ReLU        │
│ Optimizer: Adam         │
│ Loss: Mean Square Error │
└────────────┬────────────┘
             │
             ▼
      Predicted Values
             │
             ▼
    Next 10 Days Prediction

---

## 🚀 Installation

### Prerequisites

Ensure you have the following installed and configured before proceeding:
- **Flutter SDK**: `3.0.0` or higher
- **Dart SDK**: `2.17.0` or higher
- **Android Studio** / **Xcode**
- A **Firebase** account
- An **OpenWeatherMap** API key
- A **Google Cloud** account (for Gemini API)

### Setup Instructions

1. **Clone the repository**
   ```bash
   git clone [https://github.com/yourusername/AgriSage.git](https://github.com/yourusername/AgriSage.git)
   cd AgriSage

```

2. **Install dependencies**
```bash
flutter pub get

```


3. **Configure API keys**
Create a file named `lib/secrets.dart` with the following structure:
```dart
class Secrets {
  static const apiKey = 'YOUR_GEMINI_API_KEY';
  static const weatherApiKey = 'YOUR_OPENWEATHERMAP_API_KEY';
}

```


*Note: Also fill up your Firebase configuration in `lib/firebase_options.dart`.*
4. **Setup Firebase**
* Follow the official [Firebase Flutter Setup Guide](https://firebase.google.com/docs/flutter/setup?utm_source=gemini).
* Add your `google-services.json` (for Android) and `GoogleService-Info.plist` (for iOS) to their respective directories.


5. **Run the application**
```bash
flutter run

```

---

## 🌍 Google Solution Challenge Submission

AgriSage directly aligns with and addresses the following **UN Sustainable Development Goals (SDGs)**:

* **SDG 2: Zero Hunger**
* **SDG 12: Responsible Consumption and Production**
* **SDG 13: Climate Action**
* **SDG 15: Life on Land**

The application helps improve agricultural productivity while promoting sustainable practices, reducing resource waste, adapting to climate change, and preserving local ecosystems.

---

## 🙏 Acknowledgments
* **Google** for powering the AI assistant via the Gemini API.
