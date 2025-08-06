# 🎵 Spotify 2024 Most Streamed Songs Analysis

<div align="center">
  <img src="https://img.shields.io/badge/Python-3.8+-blue?style=flat&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Pandas-Data%20Analysis-orange?style=flat&logo=pandas&logoColor=white" alt="Pandas">
  <img src="https://img.shields.io/badge/Matplotlib-Visualization-red?style=flat&logo=matplotlib&logoColor=white" alt="Matplotlib">
  <img src="https://img.shields.io/badge/Seaborn-Statistical%20Plots-lightblue?style=flat" alt="Seaborn">
</div>

## Dataset Information

**Source**: [Most Streamed Spotify Songs 2024](https://www.kaggle.com/datasets/nelgiriyewithana/most-streamed-spotify-songs-2024)
- **4,598 tracks** across 27 variables (1987-2024)
- Track metadata, streaming statistics, and platform metrics
- Multi-platform data: Spotify, YouTube, TikTok, Pandora

## Project Overview

Comprehensive exploratory data analysis of the most streamed songs on Spotify in 2024, exploring streaming patterns, platform performance, and factors that drive musical success in today's digital landscape.

## Objectives

- **Identify** key factors driving song popularity across platforms
- **Analyze** streaming patterns and artist performance trends  
- **Compare** cross-platform metrics (Spotify, YouTube, TikTok)
- **Explore** temporal trends and content impact on success
- **Generate** data-driven insights for the music industry

## Key Findings

- **Platform Dominance**: TikTok shows 33x higher engagement than YouTube
- **Content Neutrality**: Explicit content (36%) performs equally to non-explicit
- **Streaming Inequality**: Few viral hits dominate while most tracks underperform
- **Temporal Growth**: 2023 peak with 1,200+ track releases
- **Cross-Platform Success**: Strong correlation between likes and views (0.94-0.99)

## Technologies Used

| Technology | Purpose |
|------------|---------|
| **Python 3.8+** | Core programming language |
| **Pandas** | Data manipulation and analysis |
| **NumPy** | Numerical computing |
| **Matplotlib** | Data visualization |
| **Seaborn** | Statistical plotting |
| **Jupyter Notebook** | Interactive development |

## Project Structure

```
spotify-2024-analysis/
├── 📂 Data/
│   ├── spotify_raw_backup.csv
│   ├── spotify_cleaned.csv
│   └── Most Streamed Spotify Songs 2024.csv
├── 📂 scripts/
│   ├── 01_data_loading_exploration.ipynb
│   ├── 02_data_cleaning.ipynb
│   ├── 03_exploratory_data_analysis.ipynb
├── 📂 Visualizations/
│   ├── artists_popularity.png
│   ├── correlation_heatmap.png
│   └── distribution_analysis.png
│   ├── platform_comparison.png
│   ├── temporal_trends.png
│   └── top_artists_streams.png
├── 📂 Documentation/
│   ├── cleaning_documentation.md
│   └── findings_summary.md
├── requirements.txt
└── README.md
```

## Analysis Workflow

1. **Data Loading & Exploration** → Initial data understanding and quality assessment
2. **Data Cleaning** → Handling missing values, data types, and outliers  
3. **Exploratory Data Analysis** → Statistical analysis, correlations, and distributions
4. **Insights & Conclusions** → Key findings and business recommendations

## Sample Results

**Top Performers:**
- Most Streamed: "Blinding Lights" by The Weeknd (4.1B streams)
- Most Productive: Taylor Swift & Drake (64 tracks each)
- Cross-Platform Kings: Bad Bunny & The Weeknd (37B total streams)

**Statistical Insights:**
- Right-skewed distributions across all platforms
- Log transformation improves data normality
- Strong positive correlations within platform ecosystems

## About This Project

This is my first comprehensive Python data analysis project, focusing on music streaming analytics and exploratory data analysis. The project demonstrates end-to-end data science skills, from raw data cleaning and statistical analysis to actionable insights for the music industry, using Python's data science ecosystem.

**Technical Skills Demonstrated:**
- **Data Cleaning**: Missing value handling, dtype optimization, duplicate removal
- **Statistical Analysis**: Correlation matrices, distribution analysis, log transformations
- **Data Visualization**: Advanced plotting with Matplotlib/Seaborn, custom styling
- **Exploratory Analysis**: Outlier detection, temporal trends, cross-platform comparison
- **Python Proficiency**: Pandas manipulation, NumPy operations, custom functions
- **Business Intelligence**: Insight generation and data-driven recommendations

---

**Note**: This analysis is for educational and portfolio demonstration purposes. All findings are based on publicly available streaming data and should be considered alongside additional market research for business decisions.
