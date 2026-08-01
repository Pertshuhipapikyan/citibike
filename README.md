# 🚲 Citi Bike Jersey City Data Analytics Project

> **A complete data analytics project that demonstrates data collection, cleaning, SQL database integration, geospatial analysis, and visualization using Jersey City Citi Bike trip data.**

![Python](https://img.shields.io/badge/Python-3.12-blue?logo=python)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-blue?logo=postgresql)
![PostGIS](https://img.shields.io/badge/PostGIS-Spatial-success)
![Docker](https://img.shields.io/badge/Docker-blue?logo=docker)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)
![GeoPandas](https://img.shields.io/badge/GeoPandas-Geospatial-green)

---

# 📖 Project Overview

This project analyzes **Jersey City Citi Bike** trip data using Python, PostgreSQL, and PostGIS.

It demonstrates a complete analytics workflow, from downloading raw trip data to building spatial datasets and visualizing ride patterns.

The project includes:

- Downloading Citi Bike trip data
- Cleaning and enriching ride records
- Collecting historical weather data
- Loading datasets into PostgreSQL
- Creating spatial station tables in PostGIS
- Performing neighborhood-level geospatial analysis
- Building interactive visualizations
- Updating the database with newly released Citi Bike data (2026)

This project was developed as part of my learning journey in **Data Analytics**, combining Python, SQL, geospatial analysis, and data visualization using real-world transportation data.

---

# 🚀 Project Features

- 📥 Download Jersey City Citi Bike monthly trip data
- 🧹 Clean and enrich trip records
- 🌦 Download historical weather data
- 🗄 Store datasets in PostgreSQL
- 🗺 Create PostGIS spatial tables
- 📍 Perform neighborhood-level geospatial analysis
- 📊 Build interactive charts and maps
- 🔄 Incrementally update the database with new monthly datasets
- 🚉 Detect newly introduced Citi Bike stations
- ✅ Prevent duplicate inserts into PostgreSQL

---

# 🏗 Project Workflow

```text
                    Citi Bike Monthly Data
                             │
                             ▼
                  Download & Extraction
                             │
                             ▼
                  Data Cleaning & Enrichment
                             │
              ┌──────────────┴──────────────┐
              ▼                             ▼
      Historical Weather            PostgreSQL
           Collection                  Storage
              │                             │
              ▼                             ▼
      Weather Dataset            PostGIS Spatial Tables
              │                             │
              └──────────────┬──────────────┘
                             ▼
                Neighborhood Analysis
                             │
                             ▼
                  Visualization & Insights
```

---

# 🛠 Technologies

| Category | Technologies |
|----------|--------------|
| Programming | Python |
| Data Analysis | Pandas, NumPy |
| Database | PostgreSQL |
| Spatial Database | PostGIS |
| Database Access | SQLAlchemy |
| Geospatial Analysis | GeoPandas, Shapely |
| Visualization | Plotly, Matplotlib, Folium |
| API | Requests |
| Containerization | Docker |
| Development | Jupyter Notebook |

---

# 📁 Project Structure

```text
citibike/
│
├── data/
│   └── citibike/
│       └── JC/
│           ├── JC2025.csv
│           ├── JC2025_Enriched.csv
│           ├── JC2026.csv
│           ├── jersey_weather_2025.csv
│           ├── jersey_weather_2026.csv
│           ├── jersey-city-neighborhoods.geojson
│           ├── JC-2025*.csv
│           └── JC-2026*.csv
│
├── notebooks/
│   ├── 1_Download_Citibike_Jersey_Data.ipynb
│   ├── 2_Data_Enrichment.ipynb
│   ├── 3_Weather_Data.ipynb
│   ├── 4_Data_Visualization.ipynb
│   ├── 5_Neighborhood_Analysis.ipynb
│   ├── 6_SQLAlchemy.ipynb
│   └── 7_Remaining_data.ipynb
│
├── postgis_data/
├── docker-compose.yaml
├── .gitignore
└── README.md
```

---

# 🗄 Database Integration

The project stores processed datasets inside PostgreSQL/PostGIS.

| Table | Description |
|--------|-------------|
| **jersey_city** | Citi Bike trip records |
| **jersey_weather** | Daily weather observations |
| **jc_2025_stations** | Spatial station table |

---

# 📒 Notebook Description

## 1️⃣ Download Citi Bike Jersey City Data

Downloads monthly Jersey City Citi Bike trip data.

**Main Tasks**

- Generate monthly download periods
- Download Citi Bike archives
- Extract ZIP files
- Merge monthly datasets
- Remove duplicate rides
- Export yearly trip dataset

**Output**

- `JC2025.csv`
- `JC2026.csv`

---

## 2️⃣ Data Enrichment

Transforms raw trip data into an analysis-ready dataset.

**Main Tasks**

- Clean raw data
- Convert datetime columns
- Calculate ride duration
- Remove invalid rides
- Create temporal features
- Create seasonal features

**Output**

- `JC2025_Enriched.csv`

---

## 3️⃣ Weather Data

Downloads historical weather data corresponding to Citi Bike ride dates.

**Main Tasks**

- Retrieve weather data from Open-Meteo
- Process daily weather variables
- Align weather with trip dates
- Export weather dataset

**Output**

- `jersey_weather_2025.csv`
- `jersey_weather_2026.csv`

---

## 4️⃣ Data Visualization

Creates visualizations for exploratory data analysis.

Includes:

- Daily ride trends
- Monthly trends
- Seasonal trends
- Weather comparison
- Interactive maps

Libraries used:

- Plotly
- Matplotlib
- Folium

---

## 5️⃣ Neighborhood Analysis

Performs geospatial analysis using GeoPandas.

**Main Tasks**

- Create station spatial tables
- Generate GeoDataFrames
- Perform spatial joins
- Aggregate rides by neighborhood
- Build neighborhood-level maps

---

## 6️⃣ SQLAlchemy

Creates the PostgreSQL connection used throughout the project.

**Main Tasks**

- Load environment variables
- Create SQLAlchemy engine
- Connect to PostgreSQL
- Verify database connection

---

## 7️⃣ Remaining Data

Extends the original project with an incremental database update workflow.

**Main Tasks**

- Download remaining 2026 Citi Bike data
- Append new trip records to PostgreSQL
- Download remaining weather data
- Append weather records
- Compare 2026 station data with the existing station table
- Detect newly introduced stations
- Update the spatial station table without creating duplicates

---

# ▶️ Recommended Execution Order

Run the notebooks in the following order:

```text
1 → Download Citi Bike Data

2 → Data Enrichment

3 → Weather Data

4 → Data Visualization

5 → Neighborhood Analysis

6 → SQLAlchemy

7 → Remaining Data
```

---

# ⚙ Installation

## Clone the repository

```bash
git clone https://github.com/Pertshuhipapikyan/citibike.git

cd citibike
```

---

## Create a Conda environment

```bash
conda create -n citibike python=3.12

conda activate citibike
```

---

## Install dependencies

```bash
pip install -r requirements.txt
```

or

```bash
conda install pandas geopandas matplotlib plotly folium sqlalchemy psycopg2 requests ipykernel
```

---

# 🐳 Docker & PostgreSQL

Start PostgreSQL/PostGIS:

```bash
docker compose up -d
```

Verify the container:

```bash
docker compose ps
```

Stop the container:

```bash
docker compose down
```

---

# 🔐 Environment Variables

Create a `.env` file in the project root.

Example:

```text
DB_USER=postgres
DB_PASSWORD=your_password
DB_HOST=localhost
DB_PORT=5432
DB_NAME=postgres
```

---

# 📊 Project Outputs

The project produces:

- Cleaned Citi Bike datasets
- Historical weather datasets
- PostgreSQL database
- PostGIS spatial tables
- Interactive visualizations
- Neighborhood analysis
- Station-level spatial analysis

---

# 🎯 Skills Demonstrated

This project demonstrates practical experience with:

- Python for Data Analysis
- Data Cleaning
- Exploratory Data Analysis (EDA)
- SQL & PostgreSQL
- SQLAlchemy
- Docker
- GeoPandas
- PostGIS
- Geospatial Analysis
- Data Visualization
- Incremental Data Updates

---

# 🔮 Future Improvements

Possible future enhancements include:

- Interactive Power BI dashboard
- Tableau dashboard
- Automated monthly data updates
- Ride demand forecasting
- Additional weather indicators
- Interactive Streamlit application

---

# 👩‍💻 Author

**Pertshuhi Papikyan**

GitHub: https://github.com/Pertshuhipapikyan
