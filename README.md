# a3-QIXIN-ACT

## 1. Exploratory Data Analysis

### Notebook with Code

+ Jupyter notebook with all necessary steps and annotations to ensure reproducibility: [Q1.ipynb](https://github.com/macs30123-s24/a3-QIXIN-ACT/blob/main/Q1.ipynb)

### Visualizations with Descriptions



## 2. Implementing a Reproducible Machine Learning Pipeline

### (ab)

+ Step1 Jupyter notebook - run locally to set up Spark EMR cluster: [Q23-Step1.ipynb](https://github.com/macs30123-s24/a3-QIXIN-ACT/blob/main/Q23-Step1.ipynb)

+ Step2 Jupyter notebook - run on Spark EMR cluster: [Q23-Step2.ipynb](https://github.com/macs30123-s24/a3-QIXIN-ACT/blob/main/Q23-Step2.ipynb)

### (b)

When specifying a series of transformations in a Spark pipeline, the DataFrame is not immediately processed. Instead, Spark uses lazy evaluation to build a logical plan outlining the transformations. This plan is optimized but not executed until an action like fit, transform, or collect is called. Upon triggering an action, Spark's Catalyst optimizer converts the logical plan into a physical plan, which is then executed across the cluster.

This approach allows Spark to optimize the execution plan, ensuring efficient resource use. In contrast, Dask also employs lazy evaluation, building a task graph that is executed only when compute is called. Both systems delay execution for optimization, but Spark uses Catalyst for query optimization, while Dask relies on its task scheduler.

## 3. Finding Optimal Model Parameters

+ Jupyter notebook - based on pipeline create in Q2 and need to be run on Spark EMR cluster: [Q23-Step2.ipynb](https://github.com/macs30123-s24/a3-QIXIN-ACT/blob/main/Q23-Step2.ipynb)

### Report and interpret the optimal model’s predictive performance

The model evaluation shows a Root Mean Squared Error (RMSE) of 1.967, indicating that predictions are, on average, about 1.967 units away from actual tip amounts. The model uses a regularization parameter (regParam) of 0.09 and an elastic net parameter (elasticNetParam) of 0.0, emphasizing L2 regularization.

Key predictors of tip amounts include pickup location and time of day. Trips from Newark (EWR) significantly increase tips, while early morning hours and weekends tend to decrease them. We can tell that hour_of_day and PUBorough might be the most relevant features for predicting tip amount because many of their one-hot encoded features have high coefficients among all features.


