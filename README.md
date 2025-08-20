# NBA Simple ETL

This is the first edition of my **Fantasy Basketball ETL prototype**.  
The goal of this project is to practice building a simple **ETL (Extract, Transform, Load)** pipeline with NBA stats, and store the processed data into a database for further analysis.

---

## 📊 Project Overview
- **Extract**: Load NBA stats from a CSV file (e.g., `nba_2425_stats.csv`).
- **Transform**: Add calculated fantasy basketball points (`fb_points`) and clean up data.
- **Load**: Save both raw stats and transformed stats into a local SQLite database (`nba.db`).

---

## 🗂️ Project Structure
nba_simple_etl/
│── fb_simple_etl.ipynb # Main ETL notebook
│── nba_2425_stats.csv # Input dataset (NBA stats for 24/25 season)
│── nba.db # SQLite database (ignored in .gitignore)
│── requirements.txt # Dependencies
│── README.md # Project documentation


## ⚙️ Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/jasonhtchen/nba_simple_etl.git
   cd nba_simple_etl
   
2. (Optional) Create and activate a virtual environment:

python -m venv venv
source venv/bin/activate   # macOS/Linux
venv\Scripts\activate      # Windows


3. Install dependencies:

pip install -r requirements.txt

🚀 Usage

Open Jupyter Notebook:

jupyter notebook


Run through fb_simple_etl.ipynb:

Reads nba_2425_stats.csv

Cleans and transforms data

Writes results into nba.db (SQLite)

Query SQLite database:

import sqlite3
import pandas as pd

conn = sqlite3.connect("nba.db")
df = pd.read_sql("SELECT * FROM player_stats_fantasy LIMIT 10;", conn)
print(df)
conn.close()

📌 Notes

nba.db is included in .gitignore (not pushed to GitHub).

You can recreate the database by re-running the ETL notebook.
