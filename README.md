
This project leverages deep learning to predict weather conditions based on historical weather data. Using a Long Short-Term Memory (LSTM) model, the system forecasts five weather parameters: **Temperature**, **Humidity**, **Wind Speed**, **Visibility**, and **Pressure** for the next day based on the previous 5 days data.

---
## **Table of Contents**
- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Installation](#installation)
- [Model Architecture](#model-architecture)
- [How It Works](#how-it-works)
- [Results](#results)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

---

## **Project Overview**
Weather forecasting is critical for planning and decision-making across various sectors. This project employs a deep learning model that:
- Takes **5 days of weather data** as input.
- Predicts **5 weather parameters** for the next day:
  - **Temperature** (°C)
  - **Humidity**
  - **Wind Speed** (km/h)
  - **Visibility** (km)
  - **Pressure** (millibars).

---

## **Dataset**
The dataset used in this project is `weatherHistory.csv`, which contains historical weather data with the following features:
- **Formatted Date**
- **Summary**
- **Precip Type**
- **Temperature (C)**
- **Apparent Temperature (C)**
- **Humidity**
- **Wind Speed (km/h)**
- **Wind Bearing (degrees)**
- **Visibility (km)**
- **Pressure (millibars)**
- **Daily Summary**

### Preprocessing Steps:
1. Irrelevant columns (`Formatted Date`, `Summary`, `Daily Summary`) are dropped.
2. Missing values in the `Precip Type` column are replaced with `'none'`.
3. Categorical data (`Precip Type`) is one-hot encoded.
4. Features are normalized using **MinMaxScaler**.

---

## **Installation**
Follow these steps to set up the project in Google Colab or a local Python environment:

1. Clone this repository:
   ```bash
   git clone https://github.com/ns-0437/weather-forecasting.git
   cd weather-forecasting
   ```

2. Install required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Upload the dataset (`weatherHistory.csv`) to your working directory if using Google Colab.

4. Run the notebook or Python script.

---

## **Model Architecture**
The LSTM-based deep learning model is implemented using TensorFlow/Keras. Key details:
- **Input**: A sequence of 5 days of weather data.
- **Layers**:
  1. LSTM layer (64 units) with return sequences.
  2. LSTM layer (32 units).
  3. Dense layer (5 units) to output predictions for the 5 parameters.
- **Loss Function**: Mean Squared Error (MSE).
- **Optimizer**: Adam.
- **Training**: 20 epochs with batch size 32.

---

## **How It Works**
1. **Input Sequences**: 
   - The model takes the weather data of the past 5 days as input.
2. **Target Variables**:
   - The model predicts 5 weather parameters for the next day.
3. **Training**:
   - The model is trained on 80% of the data, while 20% is used for validation.
4. **Evaluation**:
   - The model's performance is evaluated on unseen test data using MSE.
5. **Visualization**:
   - True vs. Predicted values for all 5 parameters are plotted.

---

## **Results**
The model demonstrates reasonable accuracy in predicting weather parameters. Below is an example of the output visualization:

- **True vs Predicted Temperatures**
- **True vs Predicted Humidity**
- **True vs Predicted Wind Speed**
- **True vs Predicted Visibility**
- **True vs Predicted Pressure**

---

## **Usage**
1. Train the model using the provided script or notebook.
2. Use the trained model to make predictions for the next day's weather.
3. Visualize results with the provided plotting functions.
