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

# Step 3: Connect Power BI to WeatherAPI
1. Open **Power BI Desktop**.  
2. Home → **Get Data** → **Web**.  
3. Paste your WeatherAPI URL (e.g. `https://api.weatherapi.com/v1/current.json?key=YOUR_API_KEY&q=CITY_NAME`).  
4. Click **OK** and wait for the preview to load.

---

# Step 4: Transform the Data
In **Power Query Editor**:  
- Select the `current` record column and click the **expand** icon (⤓) to expand it.  
- Expand nested fields like `condition` and `air_quality` (tick only fields you need).  
- Rename columns for clarity (e.g., `temp_c` → `Temperature (°C)`, `air_quality.pm2_5` → `PM2.5`).  
- Change data types (decimal number, whole number, datetime) as appropriate.  
- Remove unnecessary columns and apply any calculated columns or transformations.  
- Click **Close & Apply** to load data into your model.

**Tip:** Use Power Query parameters for `key` and `q` (city) so the query is reusable and easy to update.

---

# Step 5: Build Your Dashboard
Add visuals and layout:  
- **Cards** for current values: Temperature, Humidity, Pressure, AQI.  
- **Gauges** for wind speed or AQI ranges.  
- **Line / Area charts** for hourly/daily trends (temperature, humidity).  
- **Table / Matrix** for detailed forecast rows.  
- **Slicers** for City, Date range, Units (C/F).  
- **Map visual** to plot city locations (optional).

Arrange: top row summary cards, middle trend charts, bottom detail table/map for clarity.

---

# Step 6: Styling & Interactivity
- Add weather icons via image URLs or an images table; use conditional formatting for visuals.  
- Use **bookmarks** and **buttons** for toggles (e.g., Hourly vs Daily).  
- Edit visual interactions so selected visuals filter others as intended.  
- Configure tooltips to show extra context (time, units, data source).  
- Apply a consistent theme (backgrounds, fonts); consider semi-transparent backgrounds for a glassmorphism look.

---

# Step 7: Adding AQI Indicators with Reusable Measures
Pull AQI fields from the API (e.g., `pm2_5`, `pm10`, `us-epa-index`, or `us-epi`). Create measures to categorize AQI and drive visuals.

**AQI Category (DAX)**

```dax
AQI Category =
VAR AQIValue = SELECTEDVALUE('WeatherData'[AQI])
RETURN
SWITCH(
    TRUE(),
    AQIValue = BLANK(), "Unknown",
    AQIValue <= 50, "Good",
    AQIValue <= 100, "Moderate",
    AQIValue <= 150, "Unhealthy for Sensitive Groups",
    AQIValue <= 200, "Unhealthy",
    AQIValue <= 300, "Very Unhealthy",
    "Hazardous"
)




