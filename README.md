# 🚀 Marketing Use Case for a Classifier: Shipping Recommendation System

## 📋 Project Overview

In the context of an e-commerce business offering multiple shipping options—standard, fast, express, and in-store pickup—the goal of this project is to utilize a classifier to precisely recommend the most suitable shipping option for each customer or order. This aims to optimize both the customer experience and shipping costs. 🛒📦

## 📊 Dataset Description

The dataset contains comprehensive information about customer orders, including order IDs, shipping modes, customer details, product details, sales, discounts, profits, shipping costs, and more. The dataset represents sales and order data for a global retail company, likely collected over a period of time. It also includes additional information, such as customer demographics, shipping details, and product descriptions.

### 🏷️ Categorical Variables:

1. **Order ID**: A unique identifier for each customer order.
2. **Ship Mode**: The shipping method or mode chosen for the order (e.g., standard, express).
3. **Customer ID**: A unique identifier for each customer.
4. **Customer Name**: The name of the customer who placed the order.
5. **Segment**: The customer segment to which the customer belongs (e.g., consumer, corporate).
6. **City**: The city where the customer is located.
7. **State**: The state or province where the customer is located.
8. **Country**: The country where the customer is located.
9. **Postal Code**: The postal code or ZIP code of the customer's location.
10. **Market**: The market or market segment in which the order was placed.
11. **Region**: The region or geographic area associated with the customer's location.
12. **Product ID**: A unique identifier for each product.
13. **Category**: The product category (e.g., electronics, furniture).
14. **Sub-Category**: The sub-category of the product (e.g., laptops, chairs).
15. **Product Name**: The name or description of the product.
16. **Order Priority**: The priority level of the order (e.g., low, medium, high).

### 🔢 Numerical Variables:

1. **Row ID**: An identifier for each row or record in the dataset.
2. **Order Date**: The date when the customer placed the order.
3. **Ship Date**: The date when the order was shipped.
4. **Sales**: The total sales amount for the order.
5. **Quantity**: The quantity of products ordered.
6. **Discount**: The discount applied to the order.
7. **Profit**: The profit generated from the order.
8. **Shipping Cost**: The cost associated with shipping the order.

## 🛠️ Activities Performed

1. **Install TensorFlow Decision Forests** 🌲
2. **Load the dataset and convert it into a tf.Dataset** 📄 ➡️ 🔄
3. **Feature Engineering** 🛠️
4. **Select the Categorical and Numerical Variables required for Model Performance using Keras** 📈
5. **Encode the Categorical Labels as Integers** 🔢
6. **Split the Dataset into Training and Testing Sets** 🧪
7. **Convert the Pandas DataFrame (pd.DataFrame) into TensorFlow Datasets (tf.data.Dataset)** 🔄
   ```python
   train_ds = tfdf.keras.pd_dataframe_to_tf_dataset(train_ds_pd, label=label)
   test_ds = tfdf.keras.pd_dataframe_to_tf_dataset(test_ds_pd, label=label)
   ```
8. **Train the Model** 🏋️‍♂️
9. **Evaluate the Model** 🧮
10. **Predict Values** 🔮

## 🚀 Model Training and Evaluation

To train and evaluate the model, follow these steps:

### 1. Install Required Libraries
```bash
pip install tensorflow_decision_forests
```

### 2. Load and Prepare the Dataset
```python
import tensorflow_decision_forests as tfdf
import pandas as pd

# Load dataset
data = pd.read_csv('ecommerce.csv')

# Convert to TensorFlow Dataset
train_ds = tfdf.keras.pd_dataframe_to_tf_dataset(train_ds_pd, label=label)
test_ds = tfdf.keras.pd_dataframe_to_tf_dataset(test_ds_pd, label=label)
```

### 3. Train the Model
```python
model = tfdf.keras.RandomForestModel()
model.fit(train_ds)
```

### 4. Evaluate the Model
```python
evaluation = model.evaluate(test_ds)
print(evaluation)
```

### 5. Make Predictions
```python
predictions = model.predict(test_ds)
```

## 💡 Use Cases

Here are some potential use cases for this type of project:

- **Personalized Shipping Recommendations**: Enhancing customer satisfaction by providing tailored shipping options based on their purchase history and preferences.
- **Cost Optimization**: Reducing shipping costs by recommending the most efficient shipping method for each order.
- **Inventory Management**: Predicting shipping demand to optimize inventory levels and logistics.
- **Customer Segmentation**: Understanding customer segments better through their shipping preferences and behavior.

## 📈 Communicating Benefits to Managers

### Benefits:

1. **Improved Customer Experience**: Personalized shipping recommendations enhance the shopping experience, leading to higher customer satisfaction and loyalty.
2. **Reduced Shipping Costs**: Efficiently matching shipping options with customer needs helps minimize costs.
3. **Data-Driven Decisions**: Leveraging machine learning models provides insights that can drive strategic business decisions.

### Communication Tips:

- **Focus on ROI**: Highlight how the project can lead to cost savings and increased revenue through better customer satisfaction.
- **Data-Driven Insights**: Emphasize the importance of making decisions based on data analysis.
- **Scalability**: Explain how the solution can scale with the business as it grows.
