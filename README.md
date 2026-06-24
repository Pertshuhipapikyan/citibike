# Citi Bike Jersey City Data Analysis Project

This project analyzes Citi Bike Jersey City trip data using Python notebooks.

## Features

The project includes:

* Downloading Citi Bike Jersey City data
* Cleaning and enriching trip data
* Collecting weather data
* Creating visualizations
* Performing neighborhood-level geospatial analysis

## Project Structure

```text
.
├── README.md
├── data
│   └── JC
└── notebooks
    ├── 1_Download_Citibike_Jersey_Data copy.ipynb
    ├── 2_Data_Enrichment.ipynb
    ├── 3_Weather_Data.ipynb
    ├── 4_Data_Visualization.ipynb
    └── 5_Neighborhood_Analysis copy.ipynb
```

## 1. Create a GitHub Repository

1. Go to GitHub.
2. Click **New Repository**.
3. Enter a repository name (e.g., `citibike`).
4. Choose **Public**.
5. Click **Create Repository**.

> If the project already exists locally, do not initialize the repository with a README file.

## 2. Clone the Repository

Open a terminal and run:

```bash
git clone https://github.com/Pertshuhipapikyan/citibike.git
```



Navigate into the project folder:

```bash
cd citibike
```

## 3. Open the Project in VS Code

Open the project folder:

```bash
code .
```

If the `code` command does not work:

**File → Open Folder → citibike-jersey-city-analysis**

## 4. Create a Virtual Environment

Create a Conda environment:

```bash
conda create -n citibike python=3.12
```

Activate the environment:

```bash
conda activate citibike
```

## 5. Install Required Packages

Install the required packages:

```bash
conda install pandas geopandas folium plotly matplotlib ipykernel requests
```

When opening notebooks in VS Code or Jupyter, select:

```text
Python (citibike)
```

## 6. Recommended requirements.txt

Create a file named `requirements.txt`:

```text
pandas
geopandas
folium
plotly
matplotlib
ipykernel
requests
```

Install packages from the file:

```bash
pip install -r requirements.txt
```

## 7. Data Folder

The project stores data inside:

```text
data/JC
```

This folder is used for Jersey City Citi Bike datasets.

Raw data files should be placed or downloaded into this folder.

## 8. Notebook Explanation

The notebooks should be executed in order.

### Notebook 1: 1_Download_Citibike_Jersey_Data copy.ipynb

Downloads Jersey City Citi Bike trip data.

#### Main Tasks

* Define required time periods
* Build download URLs for Citi Bike data
* Download ZIP or CSV files
* Extract downloaded files
* Save raw data into the `data/JC` folder

> Run this notebook first because the other notebooks depend on the downloaded data.

---

### Notebook 2: 2_Data_Enrichment.ipynb

Cleans and enriches the raw Citi Bike data.

#### Main Tasks

* Load downloaded trip data
* Clean column names
* Convert date and time columns
* Create new date-related fields
* Add features such as year, month, weekday, and season
* Prepare the dataset for analysis

This notebook transforms raw data into an analysis-ready format.

---

### Notebook 3: 3_Weather_Data.ipynb

Prepares weather data for Jersey City.

#### Main Tasks

* Collect daily weather data
* Process temperature, rain, snow, precipitation, and wind fields
* Align weather data with Citi Bike trip dates
* Prepare weather data for joining with ride activity

This notebook helps analyze the relationship between weather and Citi Bike usage.

---

### Notebook 4: 4_Data_Visualization.ipynb

Creates visualizations for the project.

#### Main Tasks

* Analyze ride volume over time
* Create daily, monthly, and seasonal charts
* Compare ride activity with weather indicators
* Build visual outputs using:

  * Matplotlib
  * Seaborn
  * Plotly
  * Folium
* Support exploratory data analysis and storytelling

This notebook focuses on visual analysis.

---

### Notebook 5: 5_Neighborhood_Analysis copy.ipynb

Performs neighborhood-level geospatial analysis.

#### Main Tasks

* Use station coordinates
* Use Jersey City neighborhood boundaries
* Map Citi Bike stations to neighborhoods
* Aggregate rides by neighborhood
* Create map-based visualizations
* Use GeoPandas, Shapely, and Folium for spatial analysis

This notebook helps understand Citi Bike usage across different neighborhoods.

## 9. Suggested Notebook Execution Order

Run the notebooks in the following order:

1. `1_Download_Citibike_Jersey_Data copy.ipynb`
2. `2_Data_Enrichment.ipynb`
3. `3_Weather_Data.ipynb`
4. `4_Data_Visualization.ipynb`
5. `5_Neighborhood_Analysis copy.ipynb`

> The order is important because later notebooks depend on outputs from earlier notebooks.

## 10. Project Goal

The goal of this project is to analyze Jersey City Citi Bike usage patterns and understand how ridership changes by:

* Time
* Season
* Weather conditions
* Stations
* Neighborhoods

The project can be used for:

* Data analysis practice
* Geospatial analytics
* Dashboard preparation
* Storytelling with real-world transportation data
