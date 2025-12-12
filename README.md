# 📊 YouTube Trending Dashboard (Nigeria Region -- Daily Updates)

A fully automated analytics dashboard that tracks YouTube's trending
videos in Nigeria, updated **every morning** through a scheduled ETL
pipeline.

## 🎯 Overview

This dashboard visualizes daily insights from YouTube's trending data,
including:

-   🔥 Top 10 most viewed videos\
-   📊 Channel performance summaries\
-   📈 Daily view growth trends\
-   📉 Rank movement over time\
-   🆕 New entries to the trending chart

The data powering this dashboard is fetched daily by a separate ETL
pipeline hosted in another GitHub repository.

## 🏗 Architecture

    YouTube ETL Pipeline Repo  →  Generates CSV Results Daily via GitHub Actions  
                                 (top_videos_by_views.csv, daily_growth.csv, etc.)

    YouTube Dashboard Repo     →  Loads the CSVs from GitHub RAW URLs
                               →  Visualizes with Streamlit + Plotly
                               →  Hosted on Streamlit Cloud

## 📡 Data Source

-   YouTube Data API v3\
-   Region: NG (Nigeria)\
-   Endpoint: `videos?chart=mostPopular`

## 🚀 Features

### 🔥 Top Trending Videos

Interactive bar chart showing which videos dominate Nigerian YouTube.

### 📊 Channel Insights

Ranking creators based on total view volume.

### 📈 Daily Growth Trends

Shows the fastest-growing videos day-by-day.

### 📉 Rank Movers

How each video's trending rank changes each day.

### 🆕 New Entries

Lists new videos entering trending.

## 🧱 Tech Stack

-   Python\
-   Streamlit\
-   Pandas\
-   Plotly\
-   GitHub Actions\
-   YouTube API v3

## 📁 Directory Structure

    .
    ├── app.py
    ├── requirements.txt
    ├── assets/
    └── README.md

## 🔗 Data Sources (GitHub RAW CSVs)

-   `results/top_videos_by_views.csv`
-   `results/channel_insights.csv`
-   `results/daily_growth.csv`
-   `results/daily_rank_movement.csv`
-   `results/new_entries.csv`

## ♻️ Automatic Daily Updates

The ETL pipeline runs daily at **6 AM** and pushes new CSV files.\
The dashboard always loads the latest version automatically.

## 🛠 Running Locally

    pip install -r requirements.txt
    streamlit run app.py

## 📬 Future Improvements

-   Multi-region analysis\
-   Category-level insights\
-   Long-term trend analytics
