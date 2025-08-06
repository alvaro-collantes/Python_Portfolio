# Exploratory Data Analysis (EDA) - Most Streamed Spotify Songs 2024 

## Objective
Identify key factors driving song popularity (streams, playlists, social engagement) and compare performance across platforms (Spotify, TikTok, YouTube).

## Dataset 
- **Source**: [Kaggle](https://www.kaggle.com/datasets/nelgiriyewithana/most-streamed-spotify-songs-2024)  
- **Size**: 4,598 tracks × 27 variables  
- **Key Metrics**:  
  - Spotify Streams (100K to 4.3B per track)  
  - TikTok Views (19 to 233B)  
  - 36% explicit tracks  

## Tools
- Python (Pandas, Matplotlib, Seaborn)  
- Jupyter Notebook  

## EDA Structure Overview
For this project we follow the next procedure to obtain the **Key Findings** in order to meet our objective: 

    1. Descriptive Statistics
    2. Distribution Analysis
    3. Correlation Analysis
    4. Temporal Analysis
    5. Artist/Track Analysis
    6. Platform Comparison
    7. Explicit Content Analysis
    8. Outlier Detection
    9. Key Insights & Visualizations

## Key Findings 

### 1. Descriptive Statistics

This helps to understand the scale and distributions of the numeric data.

### Data Cleaning Challenges  
- **Issue**: Inconsistent dtypes in 4 columns (Track,Artist,Album Name and Release Date as object).  
- **Solution**: Converted to string/datetime, validated ranges (1987-2024).  

### Basic Statistics

|                            |   count |   mean |    min |    25% |    50% |    75% |    max |    std |
|---------------------------:|--------:|-------:|-------:|-------:|-------:|-------:|-------:|-------:|
|              All Time Rank |    4.6K |   2.3K |   1.00 |   1.1K |   2.3K |   3.4K |   5.0K |   1.3K |
|                Track Score |    4.6K |  41.85 |  19.40 |  23.30 |  29.90 |  44.48 | 725.40 |  38.55 |
|            Spotify Streams |    4.6K | 442.3M |   1.1K |  73.2M | 239.9M | 611.9M |   4.3B | 532.9M |
|     Spotify Playlist Count |    4.6K |  59.0K |   1.00 |   7.0K |  32.3K |  85.0K | 590.4K |  70.7K |
|     Spotify Playlist Reach |    4.6K |  23.2M |   1.00 |   4.9M |  13.3M |  29.3M | 262.3M |  29.5M |
|         Spotify Popularity |    4.6K |  64.11 |   1.00 |  62.00 |  67.00 |  71.00 |  96.00 |  14.77 |
|              YouTube Views |    4.6K | 385.7M | 913.00 |  45.8M | 148.3M | 420.3M |  16.3B | 681.1M |
|              YouTube Likes |    4.6K |   2.8M |  25.00 | 448.7K |   1.3M |   3.4M |  62.3M |   4.5M |
|               TikTok Posts |    4.6K | 750.3K |   1.00 |  67.4K | 182.5K | 460.3K |  42.9M |   2.1M |
|               TikTok Likes |    4.6K |  94.3M |   3.00 |   9.4M |  26.6M |  67.3M |  23.5B | 489.1M |
|               TikTok Views |    4.6K | 970.6M |  19.00 |  93.6M | 266.1M | 630.7M | 233.2B |   5.2B |
|     YouTube Playlist Reach |    4.6K | 290.0M |   1.00 |  22.6M |  97.7M | 232.4M |   7.3B | 601.2M |
| Apple Music Playlist Count |    4.6K |  51.37 |   1.00 |  12.00 |  28.00 |  60.00 | 859.00 |  67.68 |
|              AirPlay Spins |    4.6K |  49.8K |   1.00 | 707.25 |   6.0K |  36.4K |   1.8M | 121.8K |
|             SiriusXM Spins |    4.6K | 178.33 |   1.00 |  74.00 |  86.00 | 103.00 |   7.1K | 415.98 |
|      Deezer Playlist Count |    4.6K |  28.85 |   1.00 |   7.00 |  15.00 |  30.00 | 632.00 |  49.04 |
|      Deezer Playlist Reach |    4.6K |   1.1M |   1.00 |  83.5K | 237.4K | 608.1K |  48.2M |   3.2M |
|      Amazon Playlist Count |    4.6K |  23.43 |   1.00 |  10.00 |  17.00 |  28.00 | 210.00 |  23.08 |
|            Pandora Streams |    4.6K |  68.1M |   2.00 |   2.6M |  12.7M |  46.5M |   1.5B | 149.6M |
|     Pandora Track Stations |    4.6K |  65.8K |   1.00 |   2.7K |   7.8K |  23.6K |   3.8M | 224.9K |
|              Shazam Counts |    4.6K |   2.3M |   1.00 | 288.5K | 854.6K |   2.2M | 219.8M |   5.7M |
|             Explicit Track |    4.6K |   0.36 |   0.00 |   0.00 |   0.00 |   1.00 |   1.00 |   0.48 |

*Note: K = thousand , M = million , B = billion. Values below 1,000 are shown without suffix.*

### Findings
The metrics used to understand the popularity of tracks are divided into the following categories:

- **Volume Metrics:** Spotify Streams, YouTube Views, TikTok Views
- **Engagement Metrics:** YouTube Likes, TikTok Likes, Spotify Playlist Reach, YouTube Playlist Reach
- **Proportion Metrics:** Explicit Track

Other variables were excluded from this analysis as they do not provide relevant insights into popularity.

### Volume Metrics

For all three metrics, the **mean is significantly higher than the median**, indicating a **right-skewed distribution**:
Most songs receive relatively low numbers of streams or views, while a few highly popular tracks push the average upwards.

- **Spotify Streams:** Mean = 442.3M / Median = 239.9M → Indicates influence of high values
- **TikTok Views:** Mean = 970.6M / Median = 266.1M → Highly skewed
- **TikTok Views:** Min = 19 / Max = 233.2B → Presence of extreme outliers

### Engagement Metrics

The **standard deviation is high** for most engagement metrics, suggesting **high variability and potential instability** in user engagement:

- **TikTok Likes:** Std. Dev. = 489M → High volatility
- **YouTube Playlist Reach:** Std. Dev. = 601.2M → High volatility
- **YouTube Likes:** Std. Dev. = 4.5M → Relatively stable

### Comparison Between Platforms

- **TikTok Likes vs. YouTube Likes:**
  Avg. TikTok Likes = 94.3M vs. YouTube Likes = 2.8M → ~33x difference

- **Spotify vs. Apple Music Playlist Count:**
  Avg. Spotify Playlist Count = 59,000 vs. Apple Music Playlist Count = 51 → ~1,000x difference

### Proportion Metric: Explicit Content

- **Explicit Track:**
  36% of the dataset contains explicit content.

### Descriptive Statistics Summary

- The **mean is consistently higher than the median** for volume metrics, due to a small number of viral tracks.
- There is **extreme variability and outliers**, especially in **TikTok Views (up to 233.2B)**.
- **TikTok** dominates engagement, with **much higher likes than YouTube**.
- **Spotify** has a much broader playlist presence compared to **Apple Music**.
- **36% of tracks** are marked as explicit, which may be relevant for audience segmentation or platform restrictions

# 2. Distribution Analysis

This analysis helps to understand the shape, spread, and central tendency of the key metrics.


### Findings
All the original distributions are **right-skewed**, meaning most of the data is concentrated at lower values, with a few extreme values pulling the average upwards.
This heavy skewness suggests the presence of **outliers**, which can distort summary statistics and affect modeling performance.

After applying a **logarithmic transformation**, the distributions become more **symmetric**, closer to a bell-shaped curve.
This reduces skewness, compresses extreme values, and makes the data more suitable for statistical analysis.

Most metrics — such as Spotify Streams, YouTube Views, TikTok Likes, and Playlist Reach — show that **a small number of songs** accumulate the **majority of the views, likes, or plays**, while the vast majority remain far below the mean.

### Distribution Analysis Summary

- Original distributions are heavily skewed to the right.
- A few extreme values dominate each metric (views, likes, reach).
- Log-transformation reduces skewness and helps to normalize the data.
- Most songs perform far below average, only a small subset goes viral or reaches massive exposure.

# 3. Correlation Analysis

This analysis allows us to observe whether two variables move together, either positively or negatively.

### Findings
### Top Positive Correlations:

- **TikTok Likes and TikTok Views (0.99)**
  This suggests that TikTok videos with a higher number of likes tend to also have more views.

- **YouTube Likes and YouTube Views (0.94)**
  Similarly, YouTube videos with more likes tend to be viewed more frequently.

### Moderate Positive Correlation:

- **Spotify Playlist Count and Spotify Playlist Reach (0.86)**
  This indicates that playlists with a higher number of songs (or inclusions) tend to have a broader reach.

### Correlation Analysis Summary

The following variable pairs are strongly positively correlated:
- TikTok Likes ↔ TikTok Views (0.99)
- YouTube Likes ↔ YouTube Views (0.94)
- Spotify Playlist Count ↔ Playlist Reach (0.86)

These strong correlations suggest that the variables may be capturing the same underlying behavior.
In modeling tasks, this could raise **multicollinearity concerns**, where redundant variables may distort the interpretation of results.
To mitigate this, one variable from each highly correlated pair may be removed or prioritized based on context and modeling needs.

# 4. Temporal Analysis

This analysis allows us to understand how variables evolve over time.

### Findings
From 1987 to 2007, there were not a significant number of tracks released.
Between 2008 and 2021, the number of releases started to increase moderately.
In 2023, the number of released tracks peaked at around 1,200.
2022 and 2024 followed with approximately 700 tracks each.

Each box in the chart represents the distribution of Spotify streams (log scale) for songs released in a given year.
The boxes show the interquartile range (IQR), with the line inside indicating the median.
Dots beyond the whiskers represent outliers with stream counts far from the median.

### Temporal Analysis Summary

Starting in 2008, the year Spotify launched, a progressive increase in song streams by release year is observed.
This growth accelerated after 2015, with a clear increase in the variability and spread of the data.

The number of tracks released since 2022 has grown at a faster pace. This could be explained by a combination of factors:
- The geographic expansion of the platform
- Greater access to smartphones and internet connectivity
- An increase in new artists and releases
- Improved recommendation algorithms
- Evolving listening habits in the post-COVID era

The significant increase in outliers over the past three years suggests a growing inequality in song performance.
While many songs receive few streams, a small number of tracks accumulate extremely high numbers, highlighting a more competitive and uneven musical landscape.

# 5. Artist/Track Analysis
This analysis aims to identify the most popular artists and tracks in the dataset.

### Findings
In the Top 10 Artists by Number of Tracks, Taylor Swift and Drake lead with 64 tracks each, followed by Bad Bunny with 60 tracks.
The Weeknd ranks #5 with 31 tracks, while Peso Pluma occupies the #10 position with 22 tracks.

In the Top 10 Artists by Spotify Streams, Bad Bunny and The Weeknd share first place, each with 37 billion streams.
They are followed by Drake and Taylor Swift, with 35 and 34 billion streams respectively.

The most streamed track on Spotify is Blinding Lights by The Weeknd, with 4.1 billion streams.
The least streamed track in this category is One Dance by Drake, with 3.2 billion streams.

### Artist/Track Analysis Summary:
The Weeknd and Drake appear in all Top 10 lists.
Taylor Swift and Bad Bunny appear only in the first two categories.


# 6. Platform Comparison

This section helps us understand how songs are distributed and identify viral hits on each platform.

### Findings
For this comparison, we normalized the 4 platforms (Spotify Streams, YouTube Views, TikTok Views, Pandora Streams)
to a scale of 0 to 1 with min-max normalization, given that there are huge differences in volume between the platforms.

The boxplots, with and without outliers, show different distributions:

**Spotify Streams:** had a low outlier percentage (7%), indicating a more uniform distribution of streaming volumes.
On the other hand, there were 2 songs that were viral hits: "As It Was" and "Flowers"

**Pandora and TikTok:** had higher outlier rates (15.3% and 13.6% respectively), suggesting that few songs with high
volume reproductions are at the top of the metrics on these platforms.

**YouTube Views:** had a wide distribution with some extremely viral videos.

## Platform Comparison Summary

TikTok and Pandora have more variability in their data.
Spotify is more stable but has very extreme outliers.
Some songs are hits on all platforms (Flowers),others only on specific ones.

# 7. Explicit Content Analysis

This section examines the performance differences between explicit and non-explicit tracks across various streaming platforms.

### Findings
The dataset contains 64.1% non-explicit tracks and 35.9% explicit tracks, showing that most popular songs are clean versions.

**Spotify Streams:** Both explicit and non-explicit tracks show similar median performance, with explicit tracks having slightly more outliers in the higher range.

**Spotify Popularity:** The distributions are nearly identical between both categories, indicating that explicit content doesn't significantly impact Spotify's popularity algorithm.

**YouTube Views:** Non-explicit tracks show a wider distribution with more extreme outliers, suggesting that family-friendly content may have broader viral potential on video platforms.

**TikTok Views:** Both categories perform similarly, with comparable distributions and outlier patterns, indicating that TikTok's algorithm doesn't heavily favor either type.

## Explicit Content Analysis Summary

Explicit content does not significantly impact streaming performance across platforms.
Non-explicit tracks represent the majority (64.1%) of popular music, but explicit tracks (35.9%) perform comparably across all metrics.
YouTube shows the most noticeable difference, with non-explicit content having more viral outliers, likely due to broader audience appeal for video content.






