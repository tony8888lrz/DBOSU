# DBOSU
DSOSU: Distributed System Design for Order Supply Chain and User Behavior Analysis
# Project Overview

This project involves building a distributed computing environment using **ZeroTier**, **Docker**, and **Hadoop**, and analyzing large-scale datasets using **Spark**. The main objectives include data processing, visualization, and analysis to optimize various business functions like order processing, customer behavior analysis, and inventory management.

## Usage
Sourse code comming soon.  

## Environment Setup

### ZeroTier + Docker + Hadoop Image

- **ZeroTier**: Simulates a local area network (LAN) for connecting nodes across different physical locations, ensuring they communicate as if on the same network.
- **Docker**: Simplifies the deployment of a Hadoop cluster (NameNode and DataNode) across various environments, ensuring consistency.
- **Hadoop Docker Image**: Quickly sets up a distributed file system (HDFS) for large-scale data storage and distributed computing.

## Distributed Computing with RDD + Spark

- **RDD (Resilient Distributed Dataset)**: Used for distributed data processing.
- **Spark Master-Slave Architecture**: Tasks are managed by the **Spark Driver** and distributed across multiple **Executors**. Executors perform tasks in parallel across different nodes.
- **Driver and Executor Registration**: The Driver submits tasks to the Spark cluster, the Master assigns tasks to Executors, and the results are returned to the Driver.

## Modular Design and Execution

- **Modularization**: Each team member is responsible for a different functional module (e.g., analyzing order trends or calculating premium users).
- **Jar Packaging**: All functionalities are packaged into Jar files for easy management and execution across the cluster.
- **Task Parameterization**: Tasks can be executed by passing different parameters to modules, keeping the codebase clean and extendable.

## Data Processing and HDFS Output

- **spark-submit**: Used to submit Jar files to the Spark cluster for execution. Functionality (e.g., `region_trend` or `premium_users`) is specified via parameters.
- **HDFS Output**: Results of data processing are written to HDFS for further analysis and visualization.

## Data Visualization and Integration with Python

- **Python Tools**: Data visualization is done using **Pandas**, **Matplotlib**, and **Seaborn**. These tools read the results from HDFS and generate charts and reports.
- **Analysis**: Provides deeper insights through visualized data integration and analysis of processed results.

## Functional Modules

### 1. Order Processing and Delay Analysis

- **Objective**: Analyze order processing times to identify bottlenecks in delivery and processing.
- **Approach**:
  - Calculate the time difference between order placement and delivery.
  - Compare actual delivery dates with expected ones to identify delayed orders and categorize by region or product type.
- **Key Insight**: Helps optimize the supply chain and logistics by analyzing delays across different regions and product categories.

### 2. Customer Behavior Analysis and Segmentation

- **Objective**: Segment customers based on order history and payment patterns (e.g., **RFM Analysis**: Recency, Frequency, Monetary).
- **Approach**:
  - Analyze customer spending patterns, order frequency, and recent activity.
  - Evaluate payment preferences (e.g., credit cards, installment payments) to understand customer behavior.
- **Key Insight**: Enables personalized marketing strategies for high-value customers, frequent buyers, and customers at risk of churn.

### 3. Product Sales and Inventory Management

- **Objective**: Analyze product sales performance to optimize inventory.
- **Approach**:
  - Use order data to track sales and identify best-selling and slow-moving products.
  - Optimize storage space and shipping based on product weight, size, and sales data.
- **Key Insight**: Real-time inventory monitoring helps prioritize restocking of popular products and plan promotions for slow-moving items.

### 4. Customer Geolocation and Delivery Optimization

- **Objective**: Analyze delivery efficiency based on customer location and optimize logistics strategies.
- **Approach**:
  - Compare delivery times across regions using customer postal codes, cities, and states.
  - Identify areas with longer delivery times for route optimization.
- **Key Insight**: Customized logistics strategies (e.g., new distribution centers or optimized routes) help reduce costs and improve customer satisfaction.

## Advanced Analysis Modules

### Cross-table Data Correlation and Analysis

- **Objective**: Perform complex analyses by correlating data across multiple tables (e.g., order status, payment method, customer location, product categories).
- **Approach**:
  - Link tables such as orders, order items, customers, products, and payments to conduct multi-dimensional analysis.
  - Example: Analyze cancellation and delay rates based on payment methods and product categories.
- **Key Insight**: Provides deep insights into complex business patterns, aiding operational and marketing decisions.

### Customer Satisfaction Prediction

- **Objective**: Predict customer satisfaction using factors such as delivery time, cancellation rate, and payment method.
- **Approach**:
  - Build a predictive model using features like on-time delivery, installment payment usage, and cancellation history.
  - Target low-satisfaction customers for retention efforts or service improvements.
- **Key Insight**: Data-driven insights help improve customer experience and service quality.

### Payment Method Analysis

- **Objective**: Analyze usage of different payment methods and correlate with customer demographics.
- **Approach**:
  - Track payment method preferences (e.g., credit cards, debit cards) and installment plans through payment and order data.
  - Analyze the impact of installment payments on large purchases.
- **Key Insight**: Informs future payment system improvements and customer preferences.

### Sales Forecasting and Trend Analysis

- **Objective**: Predict future sales trends using historical data to handle demand fluctuations.
- **Approach**:
  - Use time series models or machine learning models (e.g., **ARIMA** or **LSTM**) to forecast sales.
  - Predict based on product categories, regions, and seasonal trends (e.g., holidays, promotions).
- **Key Insight**: Accurate sales forecasting optimizes inventory and production planning, minimizing excess or shortage.

### Order Cancellation and Refund Analysis

- **Objective**: Analyze the cancellation and refund rates to identify problematic products or customer behavior.
- **Approach**:
  - Use order status to calculate cancellation rates and link to product categories or regions.
  - Analyze refund data to understand high refund rates and customer dissatisfaction.
- **Key Insight**: Helps identify and address the root causes of cancellations and refunds, such as improving product quality or customer support.

## Contributors

- **Order Processing & Delay Analysis**: @rliao
- **Payment Method Analysis**: @wenzheng
- **Order Cancellation & Refund Analysis**: @shaoxi

This project showcases the powerful combination of distributed computing and modular design to solve complex business problems through data-driven insights.
