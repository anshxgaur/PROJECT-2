[1:46 pm, 15/03/2026] Ansh Gaur: Import Libraries
import yfinance as yf
import pandas as pd
import requests
from bs4 import BeautifulSoup
import matplotlib.pyplot as plt

# Configure plots
plt.style.use("seaborn")
Extract Tesla Stock Data
# Question 1: Tesla stock data
tesla = yf.Ticker("TSLA")
tesla_data = tesla.history(period="max")

# Preview
print(tesla_data.head())
print(tesla_data.tail())
Scrape Tesla Revenue Data
# Question 2: Tesla revenue data from Macrotrends
url_tesla = "https://www.macrotrends.net/stocks/charts/TSLA/tesla/revenue"
html_tesla = requests.get(url_tesla).text
soup_tesla = BeautifulSoup(html_tesla, "html.parser")

tables = soup_tesla.find_all("table")
tesla_revenue = pd.DataFrame(columns=["Date", "Revenue"])

for table in tables:
    rows = table.find_all("tr")
    f…
[1:46 pm, 15/03/2026] Ansh Gaur: # 📊 Python Project for Data Science: Tesla & GameStop Stock/Revenue Dashboards

## 🧠 Project Overview
This project involves extracting, analyzing, and visualizing historical stock and revenue data for *Tesla (TSLA)* and *GameStop (GME)* using Python. The goal is to build a dual-axis dashboard that compares stock price trends with quarterly revenue data.

## 📦 Technologies Used
- Python 3.x  
- yfinance for stock data extraction  
- requests + BeautifulSoup for web scraping revenue data
- pandas for data manipulation  
- matplotlib for data visualization  
- Jupyter Notebook for development and documentation

## 📁 Project Structure
-Question 1`: Extract Tesla stock data using yfinance
-Question 2`: Scrape Tesla revenue data from Macrotrends
-Question 3`: Extract GameStop stock data using yfinance
- Question 4: Scrape GameStop revenue data from Macrotrendss
- Question 5: Plot Tesla stock graph using make_graph function
- Question 6: Plot GameStop stock graph using make_graph function
- Question 7: Share notebook via public URL (GitHub or Watson Studio)

## 📊 Dashboard Highlights
- Dual-axis plots for each company showing:
  - Stock price over time (left y-axis)
  - Quarterly revenue trends (right y-axis)
- Clear titles, labeled axes, and gridlines for readability

## 📸 Screenshots
Screenshots of .head(), .tail(), and dashboard plots are included in the notebook as required by Coursera.

## 🔗 Submission Link
> Replace this with your public GitHub or Watson Studio URL  
> Example: https://github.com/yourusername/tesla-gme-dashboard/blob/main/project1.ipynb

## 🧹 Notes -----
- All data is sourced from public APIs and websites.
- Code is modularized for clarity and reusability.
- Markdown cells are included to explain each steps.
