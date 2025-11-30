# Broadway Lion King Ticket Price Analysis

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)

A data science project analyzing the causal impact of the 2019 Lion King movie release on Broadway ticket prices through counterfactual forecasting.

## 🎭 Project Overview

This project investigates how the release of Disney's live-action Lion King movie (July 2019) affected ticket prices for the long-running Broadway musical. Using time-series forecasting on pre-announcement data, I quantify both the immediate price response and the film's protective effect during the COVID-19 market disruption.

**Key Finding**: The movie announcement drove an 18.6% immediate price increase, and during COVID-19, actual prices declined 14.47% less than predicted, demonstrating a sustained demand-stabilization effect.

## 🎯 Motivation

The Lion King has been one of Broadway's most successful shows since 1997. When Disney announced a live-action film adaptation in 2019, it presented a natural experiment: would the movie cannibalize Broadway ticket sales, or boost them through increased brand awareness? 

By training predictive models on pre-announcement data, I could forecast "what would have happened" without the movie, then compare these counterfactual predictions against actual prices to isolate the film's causal impact.

## 📊 Methodology

### 1. Data Collection
- **Scraped 1,300+ weekly ticket price records** using Selenium from Broadway ticketing platforms
- Time period: Oct 1997 to Sep 2023
- Features: Week Endings, Avg Ticket Price ($), Top Ticket Price ($), Seats Sold Seats in Theatre,    % Cap

### 2. Exploratory Data Analysis & Data Cleaning
- Identified price anomalies and corroborated them with external events:
  - **Stagehand strikes** (2007-2008)
  - **COVID-19 pandemic** (Dec 2019 onwards)
- Handled missing values and outliers
- Performed temporal analysis to identify trends and seasonality

### 3. Time-Series Forecasting
- **Model**: Recurrent Neural Network (SimpleRNN)
- **Training data**: Pre-movie-announcement period (before April 2017)
- **Objective**: Forecast ticket prices as if the Lion King movie was never announced/released
- **Validation**: Used pre-COVID holdout set to validate model performance

### 4. Causal Impact Analysis
Compared predicted (counterfactual) vs. actual prices across two key periods:
1. **Post-announcement period** (April 2019 - July 2019): Measured immediate market response
2. **COVID-19 period** (Dec 2019+): Assessed protective effect during market disruption

## 📈 Key Results

### Immediate Impact (Post-Announcement)
- **18.6% price increase** following movie announcement
- Indicates strong positive correlation between film publicity and Broadway demand

### COVID-19 Protective Effect
- **Model prediction**: Significant price decline during pandemic
- **Actual observation**: Prices declined 14.47% less than forecasted
- **Interpretation**: The movie's brand awareness provided a demand buffer during unprecedented market disruption

### Visualization
- Please find in data-analysis-initial, sequence-model-hypertuning, or sequence-model ipynbs.

## 🛠️ Technical Stack

- **Web Scraping**: Selenium, BeautifulSoup
- **Data Processing**: Pandas, NumPy
- **Visualization**: Matplotlib, Seaborn
- **Modeling**: TensorFlow/Keras (SimpleRNN)
- **Analysis**: Scikit-learn, SciPy

## 📊 Data Sources

- Broadway ticket prices: [Playbill](https://playbill.com/production/gross/p5?production=00000150-aea5-d936-a7fd-eef572240001)

## 🔍 Future Work

- Extend analysis to other Broadway shows for comparative study
- Incorporate additional features (reviews, social media sentiment, streaming data)
- Apply more sophisticated causal inference methods (Difference-in-Differences, Synthetic Control)
- Analyze post-pandemic recovery patterns

## 🙏 Acknowledgments

- Playbill: Broadway ticketing platforms for publicly available data

---

*This project was developed as part of my portfolio demonstrating end-to-end data science methodology, from web scraping and exploratory analysis to causal inference and predictive modeling.*
