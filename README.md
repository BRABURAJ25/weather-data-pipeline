# 🌦️ Weather Data Pipeline with Python and PostgreSQL

This project demonstrates an end-to-end **ETL (Extract, Transform, Load)** data pipeline that collects real-time weather data from the **OpenWeather API**, processes it using **Python**, and stores it in a **PostgreSQL database** for further analysis or reporting.

---

## 🚀 Project Features

- 🔑 Connects to **OpenWeather API** using API keys
- 📦 Extracts real-time weather data for a specified city
- 🧹 Cleans and transforms data using Python (Pandas & JSON handling)
- 🗃️ Stores transformed data in a **PostgreSQL** table
- ♻️ Supports automation for regular updates (can be extended with scheduling tools like `cron` or `Airflow`)

---

## 🛠️ Technologies Used

- **Python 3**
- **Jupyter Notebook**
- **Requests** (API calls)
- **Pandas** (data manipulation)
- **psycopg2 / SQLAlchemy** (PostgreSQL connection)
- **PostgreSQL** (database)
- **OpenWeatherMap API**

---

## 📌 How to Run the Project

1. Clone the repo:
   ```bash
   git clone https://github.com/BRABURAJ25/weather-data-pipeline.git
   cd weather-data-pipeline
Install dependencies:

bash
Copy
Edit
pip install -r requirements.txt
Add your OpenWeather API key in the notebook.

Run the notebook:

Using Jupyter:

bash
Copy
Edit
jupyter notebook Weather_data_pipeline.ipynb


🔓 API Used
OpenWeatherMap API
Get your API key here: https://openweathermap.org/api




📊 Sample Data Points Extracted
City Name

Temperature

Humidity

Weather Description

Wind Speed

Timestamp


✍️ Author
Brabu Raj

