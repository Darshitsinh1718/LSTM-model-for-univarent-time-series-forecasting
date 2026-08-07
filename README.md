# 📈 LSTM Model for Univariate Time Series Forecasting

This project is a simple implementation of an **LSTM (Long Short-Term Memory)** network for forecasting future values in a univariate time series. The goal was to understand how recurrent neural networks work with sequential data and how they can be used to make predictions based on past observations.

## 🚀 About the Project

Time series forecasting is used in many real-world applications such as stock price prediction, weather forecasting, sales analysis, and demand estimation. In this project, I trained an LSTM model on a small univariate dataset and used it to predict upcoming values in the sequence.

The project helped me gain hands-on experience with:

* LSTM networks
* Sequence generation
* Time series data preprocessing
* TensorFlow/Keras model building
* Future value prediction

---

## 🛠️ Tools and Libraries

The following libraries were used:

* Python
* NumPy
* TensorFlow / Keras
* Matplotlib
* Jupyter Notebook

---

## 📂 Project Structure

```text
LSTM-model-for-univariate-time-series-forecasting/
│
├── LSTM_time_series.ipynb
├── README.md
└── requirements.txt
```

---

## 📊 Dataset

For this project, I used a simple univariate time series:

```python
timeseries_data = [110, 125, 134, 144, 156, 163, 170, 184, 195]
```

To train the model, the data was converted into input-output pairs using a sliding window approach.

Example:

| Input Sequence | Output |
| -------------- | ------ |
| 110, 125, 134  | 144    |
| 125, 134, 144  | 156    |
| 134, 144, 156  | 163    |

This allows the model to learn how previous values influence the next value in the sequence.

---

## 🧠 Model Architecture

The model consists of two LSTM layers followed by a Dense output layer.

```python
LSTM(50, activation='relu', return_sequences=True)
LSTM(50, activation='relu')
Dense(1)
```

Architecture:

```text
Input Sequence
      ↓
LSTM Layer
      ↓
LSTM Layer
      ↓
Dense Layer
      ↓
Predicted Value
```

---

## ⚙️ Data Preparation

A custom function was used to convert the time series into a supervised learning format.

```python
prepare_data(timeseries_data, n_steps)
```

Configuration:

```python
n_steps = 3
```

This means the model uses the previous three observations to predict the next value.

Input shape provided to the LSTM:

```python
(samples, time_steps, features)
```

Example:

```python
X.shape = (6, 3, 1)
```

---

## 🏋️ Model Training

The model was compiled using the Adam optimizer and Mean Squared Error loss function.

```python
optimizer='adam'
loss='mse'
```

Training was performed for:

```python
epochs = 250
```

---

## 🔮 Future Forecasting

Once trained, the model was used to predict the next 10 values of the series.

For prediction, the latest available sequence is provided as input, and each predicted value is added back into the sequence to generate the next prediction.

Example input:

```python
[187, 196, 210]
```

---

## 📉 Results Visualization

Matplotlib was used to visualize:

* Original time series values
* Forecasted future values

This makes it easier to observe how the model extends the trend beyond the available data.

---

## ▶️ How to Run

Clone the repository:

```bash
git clone https://github.com/your-username/LSTM-model-for-univariate-time-series-forecasting.git
```

Move to the project folder:

```bash
cd LSTM-model-for-univariate-time-series-forecasting
```

Install the required libraries:

```bash
pip install -r requirements.txt
```

Open the notebook and run all cells.

---

## 📦 Requirements

```text
tensorflow
numpy
matplotlib
jupyter
```

---

## 📚 What I Learned

Through this project, I learned:

* How LSTM networks process sequential data
* Preparing time series data for deep learning models
* Reshaping data for recurrent neural networks
* Building and training models using TensorFlow/Keras
* Forecasting future values from historical observations

---

## 🔧 Possible Improvements

Some future enhancements for this project include:

* Using larger real-world datasets
* Hyperparameter tuning
* Data normalization and scaling
* Bidirectional LSTM implementation
* GRU-based forecasting models
* Multivariate time series forecasting
* Performance evaluation using RMSE, MAE, and MAPE

---

## 👨‍💻 Author

**Darshit Chavda**

B.Tech CSE Student, IIIT Vadodara

Interested in Machine Learning, Deep Learning, Data Science, and Software Development.

If you find this project useful, feel free to give it a ⭐.
