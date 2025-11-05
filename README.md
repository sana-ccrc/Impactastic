# 🌳 AmazoCast-FM  predicting 

<p align="center">
  <img src="assets/Logo.png" alt="Project Logo" width="250"/>
  <br>
  A project by <b>Impactastic</b> 🚀
  <br>
</p>

> **Our Mission:** To leverage the power of large-scale, pre-trained Foundation Models to forecast climate trends in the Amazon, providing an impactful tool for researchers and conservationists.

This project uses IBM's **TinyTimeMixers (TTM)**, a state-of-the-art Time-Series Foundation Model (FM), to perform zero-shot and fine-tuned forecasting on temperature and precipitation data from six different regions of the Amazon.

---

## ✨ Key Features

* **Foundation Model Power:** Uses a pre-trained Time-Series Foundation Model (`granite-tsfm`) for forecasting.
* **Zero-Shot Prediction:** Generates predictions on new data *without* any prior training on that specific region.
* **Fine-Tuning Capability:** Includes code to fine-tune the model on one region's data to specialize its knowledge, improving accuracy.
* **Deep EDA:** A comprehensive Exploratory Data Analysis to understand the data's trends, seasonality, and correlations.
* **Scalable:** The code is structured to easily forecast on all 6 regions (or more).

---

## 🛠️ Tech Stack

| Category | Technology |
| :--- | :--- |
| **Core Model** | **IBM's TinyTimeMixers (TTM)** (`granite-tsfm`) |
| **Python Libs** | `transformers` (Hugging Face), `pandas`, `numpy` |
| **Data Viz** | `matplotlib`, `seaborn` |
| **ML/Data** | `scikit-learn` (for scaling) |
| **Environment** | `Python 3.10+`, `PyTorch` |

---

## 📊 Exploratory Data Analysis (EDA)

Before forecasting, we needed to understand our data. We analyzed trends, seasonality, and correlations across all regions.

<details>
<summary><b>Click to expand and see our full EDA</b></summary>
  
### 1. Temperature Over Time
We see clear seasonal patterns and different base temperatures across the six regions.
*(assets/Temperature in All Regions Over Time.png)*

### 2. Long-Term Trend
Using a 5-year rolling mean, we can see a subtle but clear upward trend in temperature in Region 1.
*(assets/Trend Analysis (using 5-year rolling mean) for region 1.png)*

### 3. Seasonality Deep-Dive
Boxplots confirm a strong, consistent seasonal cycle for both temperature and precipitation.
<p float="left">
  <img src="assets/Seasonality Boxplots (temprature).png" width="49%">
  <img src="assets/Seasonality Boxplots (precipitation).png" width="49%">
</p>

### 4. Correlation Analysis
The heatmap shows (as expected) that temperatures in different regions are highly correlated. The ACF/PACF plot confirms the strong yearly (lag 12) seasonality.
<p float="left">
  <img src="assets/Correlation Heatmap (All Variables).png" width="49%">
  <img src="assets/Autocorrelation (ACF) and Partial Autocorrelation (PACF).png" width="49%">
</p>

</details>

---

## 📈 Forecast Results: TTM in Action!

We used the TTM model to generate **zero-shot** forecasts (predicting the future without training on this data) and **fine-tuned** forecasts. The model was able to capture the seasonal patterns and trends with remarkable accuracy.

### 🌡️ Temperature Predictions
Here, the model (blue) forecasts the future, which we compare against the actual, unseen data (orange).

<p float="left">
  <img src="assets/Region3 temprature prediction.png" width="49%">
  <img src="assets/Region6 temprature prediction.png" width="49%">
</p>

### 🌧️ Precipitation Prediction
The model also does a credible job of capturing the much more volatile precipitation cycles.

<p align="center">
  <img src="assets/Region3 precipitation prediction.png" width="70%">
</p>

---

## 🔮 Future Work

* [ ] Fine-tune on *more* data to create a specialized Amazon Climate FM.
* [ ] Expand to multivariate forecasting (predicting all 6 regions at once).
* [ ] Deploy the model as a simple web app for interactive predictions.

---

## 👥 Our (Impactastic) Team

* Selina
* Sanaa
* Verrah
* Matan

---

## 🙏 Acknowledgments
* Thanks to the workshop organizers for this challenge!
* Thanks to IBM for open-sourcing the `granite-tsfm` (TinyTimeMixers) model.
