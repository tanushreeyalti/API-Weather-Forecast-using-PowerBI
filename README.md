# 🌦️ Weather Analytics Power BI Dashboard  
### Real-Time Weather, AQI & Forecast Insights  

Master data visualization with this dynamic **Weather Power BI Dashboard** – a perfect learning project for students, analysts, and developers exploring real-world data!  

🌐 **LIVE WEATHER + DATA ANALYTICS** in one powerful dashboard!  
Track real-time weather conditions, air quality index (AQI), wind, humidity, temperature trends, and location-based forecasts – all integrated into an interactive Power BI report.  

---

## 🚀 Key Features  
- 🌡️ **Real-Time Temperature & Weather Overview**  
- 💨 **Live Wind Speed, Humidity & Pressure Insights**  
- 📈 **Forecast Trends with Line & Card Visualizations**  
- 🏷️ **Air Quality Index (AQI) Display** (Good / Moderate / Poor etc.)  
- 📍 **Auto-Fetch Location Based Weather Data (City-wise)**  
- 🌐 **Clean UX with Glassmorphism Design (Modern UI Look)**  
- 🎛️ **Easy Filters for City, Country, Weather Type & More**  
- 🔌 **Powered by WeatherAPI & Dynamic M Query Integration**  

---

## 👥 Who Should Use This Dashboard  
- 🟡 **Power BI Beginners & Learners**  
- 📊 **Data Science / Analytics Students**  
- 📌 **Weather Enthusiasts & Researchers**  
- 🎨 **UI/UX Focused Developers**  
- 💼 **Freelancers & Portfolio Builders**  

---

## 🛠️ Why Get This Project?  
✔️ Built with real API data (WeatherAPI)  
✔️ Fully customizable Power BI (.pbix) file  
✔️ Clean DAX & M-code for hands-on learning  
✔️ Ideal for resume, interview prep & LinkedIn sharing  
✔️ Instantly downloadable – no coding setup needed  

---

## 📢 Disclaimer  
This dashboard is built for educational and personal learning purposes.  
All API data, weather icons, and logos belong to their respective owners.  
**Redistribution or resale is strictly prohibited.**  

# 🛠️ How to Develop a Power BI Dashboard with WeatherAPI

Power BI is a fantastic tool for visualizing data — and you can easily integrate live weather data into your reports too.  
In this guide, we’ll walk you through the process of building a real-time weather dashboard powered by **WeatherAPI**, and then we’ll add some **Air Quality Index (AQI)** indicators for a richer dashboard experience.

---

## 🎯 Why WeatherAPI?

[WeatherAPI.com](https://www.weatherapi.com/) is a simple and powerful service that returns live, historical, and forecast weather data — perfect for Power BI.  
The data is available in **JSON format**, making it easy to process and transform.

---

## 🧰 Prerequisites

Before you start, make sure you have:  

- ✅ A free or paid account on **WeatherAPI.com**  
- ✅ **Power BI Desktop** installed  
- ✅ Basic **Power BI data model** knowledge  

---

## 🔑 Step 1: Get Your WeatherAPI Key

1. Sign up at [WeatherAPI.com](https://www.weatherapi.com/).  
2. Copy your **API key**.  
3. You’ll use this key to authenticate all API calls.  

---

## 🌐 Step 2: Build the API URL

For current weather data, use the following format:

```bash
https://api.weatherapi.com/v1/current.json?key=YOUR_API_KEY&q=CITY_NAME

## 🧠 Step 3: Connect Power BI to WeatherAPI
1. Open **Power BI Desktop**.  
2. Click **Get Data → Web**.  
3. Enter your WeatherAPI URL.  
4. Click **OK**.

---

## 🧹 Step 4: Transform the Data
In the **Power Query Editor**:
- Expand the **current** record.  
- Expand sub-records like `condition` or `air_quality`.  
- Rename columns for clarity.  
- Click **Close & Apply**.

---

## 📊 Step 5: Build Your Dashboard
Add:
- ✅ **Cards** for temperature, humidity, etc.  
- ✅ **Gauges** for wind speed.  
- ✅ **Charts** for daily variations.  
Also set up **filters/slicers** for different cities.

---

## 🎨 Step 6: Styling & Interactivity
- Insert **icons** representing the current weather.  
- Plot the **map visual** with city locations.  
- Allow users to select cities dynamically.

---

## ⚡ Step 7: Adding AQI Indicators with Reusable Measures
You can incorporate **Air Quality Index (AQI)** data into your report using the `current.air_quality` section of the WeatherAPI response (create measures/columns to categorize and visualize AQI).


