# 🎾 Tennis Data Analysis

A data analysis project based on tennis match data collected from daily ZIP files.
The project focuses on data extraction, cleaning, validation, integration, exploratory analysis, and statistical investigation of tennis matches and players.

## 📌 Project Overview

In this project, we worked with tennis data stored in multiple daily ZIP files. Each daily archive contained several Parquet datasets describing different aspects of tennis matches, including match information, players, scores, tournaments, statistics, point-by-point data, odds, and tennis power metrics.

The main goal was to transform these raw and distributed datasets into a unified analytical dataset and investigate different questions related to tennis players, matches, rankings, performance, and match characteristics.

---

## 📂 Data Structure

The raw data was organized into **60 daily ZIP files**.

The project uses two main groups of datasets:

### Match-related tables

* `event`
* `home_team`
* `away_team`
* `home_team_score`
* `away_team_score`
* `tournament`
* `season`
* `round`
* `venue`
* `time`

### Additional analytical tables

* `votes`
* `power`
* `statistics`
* `point_by_point`
* `odds`

The Parquet files were extracted and combined programmatically using Python.

---

## 🔄 Data Processing Pipeline

The project follows these main steps:

1. Read the outer ZIP archive.
2. Identify the 60 daily ZIP files.
3. Extract the required Parquet files from each daily archive.
4. Combine the daily datasets for each table.
5. Check for duplicated `match_id` values.
6. Remove duplicate match records.
7. Build a unified `master` table by merging the match-related datasets.
8. Clean and validate the statistics, point-by-point, power, and odds datasets.
9. Detect and remove invalid or incomplete matches where necessary.
10. Perform exploratory and statistical analyses.

The final unified match table contains:

* **16,873 matches**
* **102 columns**

---

## 🧹 Data Cleaning & Validation

Several data quality checks were performed before the analysis.

These included:

* Duplicate `match_id` detection and removal
* Missing-value checks
* Numeric type conversion
* Validation of tennis scoring rules
* Identification of incomplete or retired matches
* Removal of invalid matches from relevant analyses
* Validation of set and game scores
* Cleaning of player and tournament information
* Handling of missing rankings and statistics

Special attention was given to ensuring that calculated metrics followed valid tennis scoring rules.

---

## 🔍 Research Questions

The project investigates a wide range of questions, including:

### Player & Match Information

1. How many tennis players are included in the dataset?
2. What is the average height of the players?
3. Which player has the highest number of wins?
4. What is the longest match recorded in terms of duration?
5. How many sets are typically played in a tennis match?
6. Which country has produced the most successful tennis players?

### Match Statistics

7. What is the average number of aces per match?
8. Is there a difference in the number of double faults based on gender?
9. Which player has won the most tournaments in a single month?
10. Is there a correlation between a player's height and their ranking?
11. What is the average duration of matches?
12. What is the average number of games per set in men's matches compared to women's matches?
13. What is the distribution of left-handed versus right-handed players?
14. What is the most common type of surface used in tournaments?
15. How many distinct countries are represented in the dataset?

### Performance & Advanced Analysis

16. Which player has the highest winning percentage against top-10 ranked opponents?
17. What is the average number of breaks of serve per match?
18. Does winning the first set predict winning the match?
19. Do seeded players actually perform better?
20. How many matches contain violations of standard tennis scoring rules?
21. Does the player with more aces have a higher probability of winning the match?
22. What percentage of matches were won by the player who took the first set?
23. Is there a relationship between a player's ranking and their probability of winning a match?

---

## 📊 Analysis & Visualization

The project uses Python for data analysis and visualization.

The analysis includes:

* Descriptive statistics
* Group-by analysis
* Win-rate calculations
* Ranking comparisons
* Correlation analysis
* Match-duration analysis
* Gender-based comparisons
* Player handedness analysis
* Tournament surface analysis
* Statistical hypothesis testing
* Data visualization

Visualizations were created using **Matplotlib** and **Seaborn**.

---

## 🧪 Statistical Analysis

For selected questions, statistical methods were used in addition to descriptive analysis.

For example, the relationship between having more aces and winning a match was tested using a **binomial test** to determine whether the observed win rate was significantly greater than 50%.

---

## 🛠️ Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **PyArrow**
* **Matplotlib**
* **Seaborn**
* **SciPy**
* **Jupyter Notebook**
* **Parquet**
* **ZIP archives**

---

## 📁 Project Structure

```text
Tennis_Data_Analysis/
│
├── Tennis_project_final.ipynb
│
├── data/
│   └── raw tennis data
│
├── figures/
│   ├── handedness_distribution.png
│   ├── tournament_surface.png
│   └── ...
│
└── README.md
```

---

## 🚀 How to Run

### 1. Clone the repository

```bash
git clone <repository-url>
cd Tennis_Data_Analysis
```

### 2. Install the required libraries

```bash
pip install pandas numpy pyarrow matplotlib seaborn scipy
```

### 3. Open the notebook

```bash
jupyter notebook Tennis_project_final.ipynb
```

### 4. Update the data path

The notebook currently expects the raw ZIP dataset to be available locally.
Update the `ZIP_PATH` variable to point to the location of the downloaded dataset.

```python
ZIP_PATH = r'path/to/tennis_data.zip'
```

---

## 📌 Key Skills Demonstrated

This project demonstrates practical experience with:

* Working with large collections of raw data files
* Reading and processing Parquet files
* Handling nested ZIP archives
* Data cleaning and preprocessing
* Data integration and table merging
* Data quality validation
* Exploratory Data Analysis (EDA)
* Feature creation
* Statistical analysis
* Data visualization
* Translating business/research questions into analytical queries

---

## 👥 Project

This project was developed as a collaborative tennis data analysis project using Python and real-world match data.
