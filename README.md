# TIME-SERIES-FORECAST-\_

## WELCOME TO MY REPO WHERE I'D TAKE YOU THROUGH MY STEP TO STEP OF TIME SERIES MODELS UNDERSTANGING.

**What is Time series Analysis**
A sequnce of observations over a certain period, Its a random sequence recorded in a time ordered fasion

**Applications of Time series**
Basically anywhere time is in a time ordered fashion
eg - Economis : Making stock marhet predictions - Social Sciences : Population Series, Birth rates, enrollments etc - Epidemiology : check for disease cases over time eg covid - In Medicine : eg to trace suger levels over time for a patient

## Types of Time Series

a) **Univariate Time series** - Consists of values taken in by a single variable at a periodic time instances of a period.

b) **Multivariate Time series** - Consists of values taken in by multiple variables at a periodic time instances over a period.

## Tools to use here

1. **Python** - Will help us data manipulation and analysis tasks
2. **Pandas** - Will allow us to load , manipulate, filter and aggregate time series data
3. **Numpy** - provides data sructures I.e:, DataFrame and series which are well suited for handling time series data
4. **SciPy (Science Python)** - Builds on numpy to allow scientific and technical computing functions - Herein , we will use SciPy for statistical analysis, statistical analysis .....
5. Atleast one visualizing library **(maplotlib, seaborn or plotly)** - Used for 2D plotting and visualizing, with plotly making the visualizations interactive
6. **datetime library** - Has 2 modules datetime and calender - Allows us parse , format, manipulate date and time information

## TIME SERIES MODELS TO GO THROUGH

(I'd explain briefly how each model works , then have a different notebook giving code examples of the implementation of each.)

1. AR MODELS
2. MA MODELS
3. ARIMA MODELS
4. SARIMA MODELS
5. SARIMAX MODELS

## IMPORTANCE OF TIME SERIES :watch:

**Time series forecasting models play a vital role in decision-making across a wide range of industries and applications. They enable organizations to make more informed, data-driven decisions, improve resource allocation, and plan for the future effectively.**

1.**Business Planning**: Time series forecasting helps businesses make informed decisions by predicting future trends in sales, demand, and revenue. This aids in inventory management, resource allocation, and financial planning.

2. **Resource Allocation**: Companies can use time series forecasts to allocate resources efficiently. For example, a manufacturing company can adjust production levels based on demand forecasts to avoid overproduction or stockouts.

3. **Financial Markets**: In finance, time series forecasting is crucial for predicting stock prices, interest rates, and exchange rates. Traders and investors use these forecasts to make investment decisions and manage risk.

4. **Energy Management**: Time series forecasting is used in the energy sector to predict electricity demand, optimize energy production, and improve the efficiency of power generation and distribution.

5. **Weather Forecasting**: Meteorologists use time series models to predict weather patterns, temperature, precipitation, and other climate-related variables. This information is vital for agriculture, transportation, and disaster preparedness.

6. **Healthcare**: In healthcare, time series forecasting is employed to predict patient admission rates, disease outbreaks, and the demand for medical supplies. It helps hospitals and healthcare providers plan for contingencies.

7. **Environmental Monitoring**: Time series forecasting is used to predict environmental variables such as air quality, water quality, and pollution levels. This data is used for environmental management and policy development.

8. **Supply Chain Management**: Companies rely on time series forecasting to optimize their supply chains. It helps in determining the right quantities of raw materials, components, and finished products to maintain smooth operations.

9. **Traffic and Transportation**: Time series models can predict traffic patterns, public transportation demand, and congestion levels. This information is valuable for urban planning and transportation infrastructure management.

10. **Marketing and Sales**: Marketers use time series forecasting to predict customer behavior, sales trends, and the effectiveness of marketing campaigns. This aids in marketing strategy development and budget allocation.

11. **Quality Control**: Time series forecasting can be applied to monitor and control product quality in manufacturing processes, helping to identify defects and maintain consistent product quality.

12. **Economic Policy**: Governments and central banks use time series models to forecast economic indicators such as GDP growth, inflation, and unemployment rates. These forecasts inform monetary and fiscal policy decisions.

13. **Customer Service**: Companies use time series forecasting to predict customer service demand, allowing them to allocate resources and staff efficiently to handle customer inquiries and issues.

14. **Risk Management**: Time series forecasting is crucial in risk assessment and management. It helps in identifying potential risks and developing strategies to mitigate them.

15. **Scientific Research**: Time series analysis is used in various scientific fields to model and predict phenomena like climate change, population growth, and the spread of diseases.

# THE AR MODEL

Auto Regression Model - Is a regression model that makes a prediction of the current value based on the past value from that time series.
Since the **previous value does not change** instanteneously, then it means that that the current value is based on the nearby previous value / values.

**An advanced definition** is A linear model where current value are a sum of past outcomes multiplied by a numeric factor.

The AR(p) model (where "p" represents the order of the model) can be expressed as follows:
The formular is

**'X*t = c + φ₁X*(t-1) + φ₂X*(t-2) + ... + φₚX*(t-ₚ) + ɛₜ'**

Where:

- `X_t` is the value of the time series at time "t," which you want to predict.
- `c` is a constant (intercept term).

- `φ₁, φ₂, ..., φₚ` are the autoregressive coefficients, which represent the weights or contributions of the previous `p` time steps to the current value `X_t`. -**This value should noy be greater than 1 at any given instance, I will explain later mathematically**
- `X_(t-1), X_(t-2), ..., X_(t-ₚ)` are the lagged values of the time series at time steps `t-1, t-2, ..., t-ₚ`.
- `ɛₜ` is the white noise error / difference between the predicted value and actual value term at time "t," representing random, unexplained variations in the time series.
- **this one accounts for the errors**

The order `p` determines how many lagged values are considered when making predictions. For example, an AR(1) model only considers the previous value (`X_(t-1)`), while an AR(2) model considers both `X_(t-1)` and `X_(t-2)`, and so on.

The goal in estimating an AR model is to find the values of the autoregressive coefficients (`φ₁, φ₂, ..., φₚ`) and the constant "c" that best fit the historical data, typically using statistical methods such as least squares estimation.

Once the coefficients are estimated, you can use the model to make forecasts by substituting the known lagged values for `X_(t-1), X_(t-2), ..., X_(t-ₚ)` into the equation to predict the value of `X_t`.

Keep in mind that the choice of the order `p` is an important consideration when building an AR model, and it often requires experimentation and model evaluation to determine the most appropriate order for a given time series dataset.
