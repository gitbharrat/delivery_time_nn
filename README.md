<a href="https://studiolab.sagemaker.aws/import/github/gitbharrat/delivery_time_nn/tree/main/notebook/delivery_time_estimation.ipynb">
  <img src="https://studiolab.sagemaker.aws/studiolab.svg" alt="Open In SageMaker Studio Lab"/>
</a>

# **🚀 Delivery Time Estimation with Neural Networks**

> **⚠️ Warning:** This repository is currently a work in progress. Contributions are welcome, but please note that the project is still under development and subject to changes.

This project involves developing a delivery time estimation model for a leading intra-city logistics marketplace in India. The company aims to enhance the lives of over 150,000 driver-partners by providing consistent earnings and independence. Currently, the company has serviced over 5 million customers.

The company collaborates with various restaurants to deliver items directly to customers. Our objective is to estimate delivery times based on features such as order details, restaurant category, and available delivery partners.

### Dataset

Each row in this dataset corresponds to a unique delivery. Each column represents a feature, explained below:

| Column Name             | Description                                                                                     |
|-------------------------|-------------------------------------------------------------------------------------------------|
| **market_id**           | Integer ID for the market where the restaurant is located                                       |
| **created_at**          | The timestamp when the order was placed                                                         |
| **actual_delivery_time**| The timestamp when the order was delivered                                                      |
| **store_primary_category** | Category of the restaurant                                                                   |
| **order_protocol**      | Integer code for the order protocol (e.g., through the company, call to restaurant, pre-booked, third-party, etc.) |
| **total_items**         | Total number of items in the order                                                              |
| **subtotal**            | Final price of the order                                                                        |
| **num_distinct_items**  | Number of distinct items in the order                                                           |
| **min_item_price**      | Price of the cheapest item in the order                                                         |
| **max_item_price**      | Price of the costliest item in the order                                                        |
| **total_onshift_partners** | Number of delivery partners on duty when the order was placed                                |
| **total_busy_partners** | Number of delivery partners attending to other tasks                                            |
| **total_outstanding_orders** | Total number of orders to be fulfilled at the moment                                       |

## Process

#### **🔍 Import the Data and Understand the Structure using PySpark:**
   - Perform exploratory analysis to check the structure and characteristics of the dataset.

#### **🛠️ Data Preprocessing:**
   - Clean the data 🧹
   - Create the target column (time taken for each delivery) from order timestamp (created_at) and delivery timestamp (actual_delivery_time).
   - Extract the hour of the day and day of the week from the order time 📅
   - Handle null values 🛠️
   - Encode categorical columns 🔄

#### **📊 Data Visualization and Cleaning using Plotly:**
   - Visualize various columns for better understanding (e.g., countplots, scatterplots) 📊
   - Check for outliers 🔍
   - Remove outliers using appropriate methods 🚫
   - Plot the data again to see improvements 📈

#### **🧠 Model Building using PyTorch**
   - Split the data into train and test sets 🧪
   - Scale the data for neural networks 📏
   - Create a simple neural network using modern technologies like PyTorch 🧠
   - Train the neural network for the required number of epochs 🏋️
   - Plot the losses and check the accuracy of the model 📉
   - Evaluate using various metrics like MSE, RMSE, and MAE 📐
   - Use MLflow for model versioning: Track experiments and model versions using MLflow to maintain a record of different models and their performance over time.

#### **⚙️ Hyperparameter Tuning using Hyperopt**
   - Experiment with different configurations, activation functions, optimizers, and other hyperparameters using Bayesian optimization with Hyperopt ⚙️
   - Use Hyperopt to find the optimal hyperparameters for the neural network
   - Evaluate the performance of the tuned model

#### **🌟 Model Explanation using LIME**
   - Use LIME (Local Interpretable Model-agnostic Explanations) to explain the predictions of the neural network
   - Generate explanations for individual predictions to understand the model's decision-making process
   - Visualize the impact of different features on the model's predictions

---
