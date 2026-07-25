# Chronos Forecasting Tool

## Helping analysts and planners generate reliable predictions from historical time series data

Organisations often need to forecast what will happen next. This could be demand for a service or a resource or any other metric that changes over time. Producing a good forecast is not straightforward, and no single method is right for every dataset.

Chronos is an interactive forecasting tool that trains multiple machine learning models simultaneously, tests their performance, and combines the best-performing ones into a single ensemble forecast taking advantage of the wisdom-of-crowds effect. Rather than relying on one model that may perform poorly when conditions change, Chronos draws on the collective predictions of several independent models to produce more robust and reliable forecasts than any single model in isolation. 
<figure>
  <img src="images/5_Forecast_results_forecast_in_context.png"
       alt="Forecast chart showing historical data and future predictions with confidence bounds"
       width="600">
  <figcaption><em>Forecast chart showing historical data extended into the future, with confidence bounds showing the range of predictions across models.</em></figcaption>
</figure>

---

## The Business Problem

Many operational and planning decisions depend on having a credible view of the future. How many units will we need next quarter? Is demand rising or falling? When should we expect a seasonal peak?

Forecasting from historical data involves several competing challenges.

No single model works best for every dataset. A method that performs well on a stable, slowly-changing series may perform poorly on one with strong seasonal patterns or an underlying trend.

Uncertainty is inherent in any forecast. A single prediction line gives no indication of how confident the model is, or how much the answer might vary.

Tuning a model to perform well requires testing — but testing takes time, and doing it manually is error-prone.

The challenge is therefore to produce a forecast that is:

- grounded in the patterns present in the historical data
- generated from a well-tested and well-tuned set of models
- clear about uncertainty, with confidence bounds around the central prediction
- quick enough to be practical in a real planning workflow
- accessible to users who are not data scientists

This is exactly the type of forecasting problem where machine learning can add value: not by replacing analytical judgement, but by giving planners a rigorous, evidence-based forecast as a starting point.

---

## What the Tool Does

The app guides a user through a structured forecasting workflow in six steps.

The user uploads a file containing their historical data — a date column and a values column — and selects the appropriate time frequency. Chronos infers the frequency automatically where possible.

The data can optionally be resampled to a lower frequency, for example aggregating daily data into monthly totals. Chronos checks the data for quality issues — missing periods, outliers, zero-heavy series — and flags anything that may affect forecast quality.

The user then sets how far ahead to forecast, selects which models to include, and runs the forecast. Chronos trains each model, optimises its parameters through an automated search, and evaluates performance on held-out historical data. The best-performing combination of models is selected and used to generate the final forecast.

Results are presented through:

- a forecast chart showing the prediction appended to the full historical series
- a zoomed chart focused on the forecast period alone, with confidence bounds
- individual model forecasts showing how much models agree or disagree
- a forecast values table with min, max and combined predictions per period
- a validation chart comparing the model's back-test predictions against known historical values
- accuracy metrics including RMSE, MAPE and percentage of observations within the forecast bounds
- an ensemble weights chart showing the contribution of each model

---

## Screenshots

The screenshots below illustrate the main stages of the tool.

### Data input and frequency detection

<figure>
  <img src="images/1_Intro_and_Data_input.png"
       alt="Data input screen with file upload and frequency selector"
       width="600">
  <figcaption><em>The user uploads a CSV or Excel file. Chronos automatically infers the data frequency and asks the user to confirm it before proceeding.</em></figcaption>
</figure>

### Data aggregation and quality checks

<figure>
  <img src="images/2_Data_aggregation.png"
       alt="Data aggregation step showing resampled time series chart"
       width="600">
  <figcaption><em>Data can optionally be resampled to a lower frequency. The chart updates to show the processed series, and any quality issues are flagged automatically.</em></figcaption>
</figure>

### Forecast settings and run controls

<figure>
  <img src="images/3_Forecast_settings_and_4_Run.png"
       alt="Forecast horizon settings and run button"
       width="600">
  <figcaption><em>The user specifies how many periods ahead to forecast. The corresponding forecast dates are shown automatically. Pressing Run Forecast starts the training and evaluation process.</em></figcaption>
</figure>

### Forecast results

<figure>
  <img src="images/5_Forecast_results_forecast_in_context.png"
       alt="Forecast chart showing historical data and ensemble prediction with confidence bounds"
       width="600">
  <figcaption><em>The ensemble forecast appended to the full historical series. The shaded band shows the min/max range across the individual models, reflecting forecast uncertainty.</em></figcaption>
</figure>

<figure>
  <img src="images/5_Forecast_results_forecast_chart.png"
       alt="Zoomed forecast chart showing the forecast period only"
       width="600">
  <figcaption><em>The forecast period shown in isolation, with confidence bounds. Wider bands indicate greater disagreement between models.</em></figcaption>
</figure>

<figure>
  <img src="images/5_Forecast_results_individual_model_forecasts.png"
       alt="Individual model forecasts shown together"
       width="600">
  <figcaption><em>Each model's individual forecast before ensemble combination. This view shows how closely models agree and which are outliers.</em></figcaption>
</figure>

<figure>
  <img src="images/5_Forecast_results_data_table.png"
       alt="Forecast values table with min, max and per-model columns"
       width="600">
  <figcaption><em>Forecast values for each period, including the combined ensemble forecast and the min/max range across models.</em></figcaption>
</figure>

### Validation results

<figure>
  <img src="images/6_Validation_results_screenshot.png"
       alt="Validation chart and accuracy metrics"
       width="600">
  <figcaption><em>Validation summary showing accuracy metrics including RMSE and MAPE, calculated by testing the model against held-out historical data it was not trained on.</em></figcaption>
</figure>

<figure>
  <img src="images/6_Validation_out-of-sample_forecast_chart.png"
       alt="Back-test chart comparing model forecast to known historical values"
       width="600">
  <figcaption><em>The back-test chart comparing the model's held-out forecast (red) against the true observed values (blue), showing how well the ensemble would have performed on recent history.</em></figcaption>
</figure>

<figure>
  <img src="images/6_validation_ensemble_model_weights.png"
       alt="Bar chart showing the contribution of each model to the ensemble"
       width="600">
  <figcaption><em>The ensemble weights chart shows how much each model contributes to the final combined forecast. Models that scored better during validation receive a higher weighting.</em></figcaption>
</figure>

---

## Why This Is Useful

The value of the tool is its ability to produce a well-tested, transparent forecast without requiring the user to have any knowledge of machine learning.

Rather than asking analysts to choose a single forecasting method or tune models manually, Chronos automates the model selection and testing process and presents results in a format that can be reviewed, shared and acted on.

**More reliable forecasts through ensemble methods**

By combining multiple independent models, Chronos reduces the risk that a poorly-performing individual model distorts the forecast. The final prediction reflects the collective view across the ensemble.

**Honest about uncertainty**

The confidence bounds on the forecast charts are derived directly from the spread of predictions across individual models. Where models disagree, the bounds are wider — giving the user a clear visual signal of where forecast uncertainty is higher.

**Automated model tuning**

Chronos uses an automated parameter search to find improved settings for each model. This removes the need for manual trial and error and helps each model perform as well as possible on the specific dataset.

**Built-in validation**

Before producing a forecast, Chronos tests the chosen ensemble against a portion of the historical data it was not trained on. This gives the user an honest estimate of how accurate the forecast is likely to be, not just how well the model fitted its training data.

**Practical for repeated use**

Completed model runs are cached to disk. Re-running a forecast with the same data and settings retrieves results from cache rather than recomputing from scratch, saving time on repeated runs.

---

## The Ensemble Approach

Chronos trains up to twelve different machine learning models in parallel, covering a wide range of algorithm families:

- **K-Nearest Neighbours** — forecasts based on similarity to past patterns
- **Ridge regression** — a simple linear model that handles correlated features
- **Gradient boosting variants** (Hist Gradient Boost, XGBoost, LightGBM, Gradient Boost) — powerful tree-based models that capture complex non-linear relationships
- **Random Forest and Extra Trees** — ensemble tree models that average across many decision paths
- **Support Vector Regression** and **Kernel Ridge** — models suited to smaller datasets with complex patterns
- **Neural network (MLP)** — a multi-layer model that can learn non-linear feature interactions
- **Exponential Smoothing** — a classical statistical method suited to series with trend and seasonality

Each model is trained on the same time-indexed features derived from the historical data, including lagged values, rolling averages and calendar components such as month and day of year. Chronos then tests all valid combinations of models, selects the combination that produces the lowest error on held-out data, and uses that combination to generate the final forecast.

---

## A Note on the Analytical Approach

Chronos does not use a single fixed forecasting method.

That is an intentional design choice. Different datasets respond better to different modelling approaches, and there is no universally best model for time series forecasting. By training an ensemble and selecting the best-performing combination through cross-validated testing, Chronos adapts its approach to the specific characteristics of each dataset.

The tool handles several common data quality challenges automatically: missing periods are filled by linear interpolation before modelling, duplicate dates are summed, and negative forecasts are removed. Users are informed of any issues detected in their data before the forecast is run.

---

## What This Demonstrates

This project demonstrates several data science and product design skills:

- designing a multi-step analytical workflow for non-technical users
- implementing and evaluating an ensemble of machine learning models
- automated hyperparameter optimisation using search algorithms
- time series cross-validation and back-testing
- translating model uncertainty into interpretable visual outputs
- building a practical, production-ready interactive application
- writing clear, informative user guidance throughout the interface

The project is focused on producing a useful forecasting tool taking advantage of the wisdom-of-crowds approach. Its purpose is to show how machine learning can be packaged in a way that is accessible and applicable to real planning problems.

---

## Limitations

Machine learning models are only able to extrapolate from historical patterns. They cannot anticipate events with no precedent in the data or significant step-changes. Forecast accuracy will decline the further ahead the prediction extends.

The confidence bounds reflect disagreement between models, providing a useful indication about forecast uncertainty, rather than a formal statistical confidence interval.

All forecasts should be reviewed alongside domain knowledge and professional judgement before being used to inform decisions.

---

## Further Improvements

Potential enhancements to the tool include:

- adding more classical time series methods such as ARIMA or Prophet as ensemble members
- supporting multivariate forecasting, where additional explanatory variables can improve predictions
- allowing users to flag known future events such as promotions or holidays as forecast inputs
- adding scenario comparison, allowing two or more forecasts to be viewed side by side
- generating a summary report from the completed forecast run
- providing more detailed guidance on which models tend to perform well on different data types
- extending caching to support incremental updates when new data is appended

---

## Portfolio Reflection

This project is a useful example of applied data science because it addresses a common and practical forecasting challenge.

It shows that machine learning can be made accessible to non-technical users without sacrificing rigour. The ensemble approach, automated validation and confidence bounds all contribute to a forecast that is more trustworthy than a naive single-model prediction, while the interface keeps the complexity hidden from the user.

The strongest feature of this project is its end-to-end completeness. From raw data upload through to a validated ensemble forecast with interpretable confidence bounds, the tool handles the full analytical workflow in a single application.

---

## Repository

The code is available in the GitHub repository: [View the project repository](https://github.com/pierswalker71/chronos)

Main file:
```text
Chronos.py
```

---

## Summary

Chronos turns a CSV or Excel file of historical data into a validated ensemble forecast in a few clicks. By training multiple machine learning models in parallel, automatically selecting the best-performing combination and presenting confidence bounds alongside the central prediction, it produces forecasts that are more reliable and more open about uncertainty than a single-model approach. The tool is designed for analysts and planners who need a credible, evidence-based forecast without needing to understand the underlying machine learning methods.

---

**←[Back to selected projects](https://pierswalker71.github.io/projects)**
