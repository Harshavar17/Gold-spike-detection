# Gold Price Spike Detection and Analysis

## Overview
This repository contains a Python script that detects significant spikes in gold prices (XAU/USD) using minute-level data. It also fetches and analyzes news articles related to these price spikes to provide insights into potential causes.

## Table of Contents
1. [Introduction](#introduction)
2. [Dependencies](#dependencies)
3. [Data Collection](#data-collection)
4. [Spike Detection](#spike-detection)
5. [News Fetching](#news-fetching)
6. [Data Visualization](#data-visualization)
7. [Usage](#usage)
8. [Algorithms Used](#algorithms-used)
9. [Future Improvements](#future-improvements)

## Introduction
This script analyzes gold price data to detect significant price movements, referred to as "spikes." It also fetches news articles related to these spikes to help understand potential causes.

## Dependencies
To run the script, you need the following Python libraries:
- `yfinance` for downloading financial data.
- `numpy` for numerical operations.
- `matplotlib` for plotting data.
- `pandas` for data manipulation.
- `requests` for fetching news articles.

## Data Collection
The script fetches minute-level gold price data from Yahoo Finance using the `yfinance` library. The data is collected in chunks to handle large datasets efficiently.

### Steps:
1. **Define the Time Range**: The script fetches data for a specified period (e.g., past month).
2. **Download Data**: Data is retrieved in 7-day intervals to manage large volumes.

## Spike Detection
Spikes are detected based on predefined thresholds for slope, pip change, and value change.

### Steps:
1. **Calculate Slope**: The slope between two consecutive price points is calculated.
2. **Detect Spikes**: Spikes are identified if they exceed the predefined slope and pip thresholds or if the value change surpasses a set threshold.

### Algorithms:
- **Slope Calculation**: Measures the rate of change between price points.
- **Threshold-Based Filtering**: Applies thresholds to identify significant spikes.

## News Fetching
News articles related to detected price spikes are fetched using the NewsAPI.

### Steps:
1. **Define Query Parameters**: Specify the query and time range for news articles.
2. **Fetch Articles**: Use NewsAPI to retrieve articles related to the gold price and the detected spike.

## Data Visualization
The script plots gold price data and highlights detected spikes.

### Steps:
1. **Plot Price Data**: Visualize the gold price data over time.
2. **Highlight Spikes**: Mark detected spikes on the plot with annotations.

## Usage
To use the script, define the target date and thresholds, then call the `analyze_date` function.


![image](https://github.com/user-attachments/assets/0bf078da-0677-46c1-a967-f2ebf513192b)
![image](https://github.com/user-attachments/assets/129cb1c4-a644-4504-bf7f-a782aeca3223)


### Example:
```python
date_input = "2024-08-14"
slope_threshold = 9
pip_threshold = 750
value_threshold = 7.2
analyze_date(date_input, slope_threshold=slope_threshold, pip_threshold=pip_threshold, value_threshold=value_threshold)


