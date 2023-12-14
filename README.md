# Which Party Do Voters Favour For Congress: Republican or Democrat?

## Project Background
The United States voting system is decentralized, featuring federal, state, and local elections, and a two-party structure dominated by the Democratic and Republican Parties. Primary elections precede the general election, and the Electoral College determines the President and Vice President. Currently in the primary elections, the general elections for the President are scheduled for 2024.

**Democratic Party:**
- **Symbol:** Donkey, originating from a 1828 campaign insult that was embraced by candidate Andrew Jackson.
- **Color:** Blue, symbolizing a calm and inclusive image.
- **Ideology:** Progressive and liberal, advocating for social justice, environmental protection, healthcare reform, workers' rights, and active government involvement in social and economic issues.

**Republican Party:**
- **Symbol:** Elephant, popularized by a 1870s political cartoon, representing strength and size.
- **Color:** Red, associated with a more conservative and traditional image.
- **Ideology:** Conservative, supporting limited government, free-market policies, lower taxes, a strong national defense, and a strict interpretation of the Constitution.

## Business Problem
The business problem is to develop a forecasting model for the future elections. By analyzing historical data on voters polls we can build a predictive model to estimate the potential number of votes each party may receive in upcoming elections. This information will help political strategists, campaign managers, and party leaders make informed decisions about resource allocation, messaging, and targeting specific voter segments to gain a competitive advantage.

## Data Understanding
In this regard, the data was sourced from https://projects.fivethirtyeight.com/polls/generic-ballot/. It comprises of a collection of generic ballot poll results conducted over a specific period of time, capturing sentiments regarding the two political parties.
The file contains the links to the following data:

1. [`generic_polllist.csv`](https://projects.fivethirtyeight.com/generic-ballot-data/generic_polllist.csv) contains a list of generic ballot polls for the current election cycle.
2. [`generic_topline.csv`](https://projects.fivethirtyeight.com/polls/data/generic_ballot_averages.csv) contains a trendline for the generic ballot from the 2018 election cycle to the present.
3. [`generic_topline_historical.csv`](./generic_topline_historical.csv) contains a trendline for the generic ballot for previous election cycles going back to 1996.

![image.png](attachment:image.png)

![image.png](attachment:image.png)

![image.png](attachment:image.png)

### Time Series Modelling

**Summary: Stationarity & Trend**

Checking for stationarity is crucial in time series analysis for various reasons:

1. **Model Assumptions:** Time series models like ARIMA and STL assume stationarity. Violating this can lead to inaccurate model results.

2. **Mean and Variance Stability:** Stationarity implies constant mean and variance over time. Non-stationary series may have trends or seasonality, complicating pattern identification and prediction.

3. **Statistical Testing:** Stationarity is often required for tests like ADF. Non-stationary series may need differencing to achieve stationarity.

4. **Model Performance:** Stationary time series are easier to model and forecast, allowing simpler models to capture patterns effectively.

5. **Interpretability:** Stationary time series are more interpretable, as their statistical properties remain constant over time.

To check stationarity, techniques include visual inspection, summary statistics, and formal tests like ADF. Non-stationary series may require transformations like differencing. When time series models are not stationary, there is a trend.

![image.png](attachment:image.png)

##### For trend checking

![image.png](attachment:image.png)

#### Time Series Decomposition**

Time series decomposition involves breaking down a time series into trend, seasonality, and residual components to better understand its patterns. The main components are:

1. **Trend & Stationarity:**
   - Represents long-term movement or direction.
   - Captures underlying growth, decline, or stability.
   - Offers insights into the overall series direction.

2. **Seasonality:**
   - Accounts for regular patterns at fixed intervals.
   - Occurs in cycles like daily, weekly, monthly, or yearly.
   - Crucial for accurate forecasting in various fields.

3. **Residual (Error):**
   - Represents random fluctuations or unexplained variability.
   - Reflects noise not attributed to trend or seasonality.
   - Helps assess model performance and identify irregularities.

![image.png](attachment:image.png)

##### Correlation, Autocorrelation and Partial Correlation

![image.png](attachment:image.png)

![image.png](attachment:image.png)

### Forecasting

### 1. ARIMA Model

![image.png](attachment:image.png)

![image.png](attachment:image.png)

#### Model Evaluation and Recommendations

The analysis involves fitting SARIMAX models for Democratic and Republican political sentiment and emphasizes the importance of thorough model evaluation. Key recommendations include:

1. **Model Evaluation:**
   - Assess diagnostic statistics and goodness-of-fit measures.
   - Examine how well models capture underlying political sentiment dynamics.

2. **Comparison with Alternative Models:**
   - Explore alternative model specifications for potential improvement.
   - Experiment with different orders for AR, MA, and seasonal components.

3. **Residual Analysis:**
   - Investigate residuals to ensure no unexplained patterns or trends.
   - Address autocorrelation revealed by Ljung-Box test for enhanced reliability.

4. **Conclusion:**
   - Democratic Party Model (dem_estimate): ARIMA(0, 1, 1) with negative MA effect.
   - Republican Party Model (rep_estimate): ARIMA(1, 0, 0) with attention to Jarque-Bera test.

5. **Next Steps:**
   - Refine model orders balancing complexity and fit.
   - Conduct thorough diagnostic analysis, addressing autocorrelation and non-normality.
   - Evaluate models on out-of-sample data for predictive accuracy.

6. **External Validation:**
   - Consider external factors impacting political sentiment for enhanced explanatory power.

7. **Stakeholder Communication:**
   - Communicate findings and limitations to stakeholders.
   - Set realistic expectations for predictive capabilities, acknowledging uncertainties.

8. **Continuous Improvement:**
   - Iteratively refine model specifications based on new data.
   - Monitor and update models to enhance accuracy over time.


```python

```
