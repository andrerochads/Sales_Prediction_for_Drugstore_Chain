# Sales Prediction

## Predicting sales from all Rossmann drugstores
<img src="https://cdn.immofinanz.com/uploads/production/5e21a7dddee6e56db91bce1c/rossmann-pila.jpg" alt="Minha Imagem">

## 1. Business Problem
<p>Rossmann drugstore is a European drugstore chain that offers a wide variety of products and has a presence in several European countries and is considered one of the largest drugstore chains in Europe.</p>
<p>The company's CFO is planning to renovate some stores and, in order to make better decisions, has requested sales forecasts for all stores for the next six weeks.</p>



## 2. Business Assumptions
<p> The assumptions about the business problem is as follows: </p>

<ul>
  <li>To account for sales data, I excluded days where stores were closed or had no sales.</li>
  
  <li>If <code>competition_distance</code> is unknown, it suggests there is no competition or the nearest competitor is too far away to impact sales, thus I assigned a distance exceeding the maximum value in the dataset.</li>
  
  <li>When <code>competition_open_since_month</code> is unknown, and it has some value in the competition_distance column, I will use the sale date, as it will be needed for the feature engineering step.</li>
  
  <li>Similarly, I applied the same reasoning to <code>competition_open_since_year</code>.</li>
  
  <li>If <code>promo2_since_week</code> is unknown, I assume the store chose not to participate in the promotion.</li>
  
  <li>I employed the same method to <code>promo2_since_year</code>.</li>
</ul>



## 3. Solution Strategy

<p><b> Step 1 - Data Description:</b> My goal is to use statistics metrics to identify data outside the scope of business. </p>  

<p><b> Step 2 - Feature Engineering:</b> Derive new attributes based on the original variables to better describe the phenomenon that will be modeled. </p> 

<p><b> Step 3 - Data Filtering:</b> Filter rows and select columns that do not contain information for modeling or that do not match the scope of the business. </p> 

<p><b> Step 4 - Exploratory Data Analysis (EDA):</b> Explore the data to find insights and better understand the impact of variables on model learning. </p> 

<p><b> Step 5 - Data Preparation:</b> Prepare the data so that the Machine Learning models can learn the specific behavior. </p> 

<p><b> Step 6 - Feature Selection:</b> Selection of the most significant attributes for training the model. </p> 

<p><b> Step 7 - Machine Learning Modeling:</b> Machine Learning model training. </p> 

<p><b> Step 8 - Hyper Parameter Fine Tuning:</b> Choose the best values for each of the parameters of the model selected from the previous step. </p> 

<p><b> Step 9 - Model Evaluation:</b> Convert the performance of the Machine Learning model into business result. </p> 

<p><b> Step 10 - Deployment:</b> Publish the model in a cloud environment so that other people or services can use the results to improve the business decision. </p> 



## 4. Top 3 Data Insights

<p><b> Hypotesis 1:</b> Stores with closer competitors should sell less. </p>
<p><b> False.</b> Stores with closer competitors sell more. </p>
![h1 chart](/images/h_competitors.png)


<p><b> Hypotesis 2:</b> Stores with more consecutives promotions should sell more.</p>
<p><b> False.</b> Stores with more consecutive promotions sell less. </p>
![h2 chart](/images/h_promotions.png)


<p><b> Hypotesis 3:</b> Stores with greater assortments should sell more. </p>
<p><b> False.</b> Stores with greater assortment sell less. </p>
![h3 chart](/images/h_assortment.png)



## 5. Machine Learning Models Applied
<p> Tests were made using different algorithms. </p>



## 6. Machine Learning Performance
<p> The MAE, MAPE and RMSE metrics evaluated the performance of the models. </p>

<p> I performed a single test to verify the linearity of the problem. </p>
![Single performance table](/images/single_performance.png)

<p> To know the real performance of the model, I applied the Cross validation technique. </p>
![Real performance table](/images/real_performance.png)

<p> 
Despite a slight performance difference over Random Forest, I chose to use XGBoost due to my interest in learning it. Also, as the project was on a storage-limited cloud platform, XGBoost required less space, making it more suitable. 
</p>

<p> The MAE, MAPE and RMSE metrics evaluated the performance of the models. </p>

<p> I performed a single test to verify the linearity of the problem. </p>
![Single Performance Table](/images/single_performance.png)

<p> To know the real performance of the model, I applied the cross-validation technique. </p>
![Real performance table](/images/real_performance.png)

<p>
Despite a small performance difference compared to Random Forest, I chose to use XGBoost due to my interest in learning it. Also, as the project was on a cloud platform with limited storage, XGBoost required less space, making it more suitable.
</p>

<p> After the algorithm selection, I also applied the fine tuning technique to it. </p>



## 7. Deployment
<p> I developed a Telegram bot that returns store sales forecasts to the user. </p>



## 8. Business Results
<p> 
The table below presents the results of the sum of sales of all stores, which in the next six weeks will generate a profit of 284.9 million in the worst case scenario or 286.6 million in the best case scenario.
</p>
![Business Results table](/images/Business Results.png)



## 9. Conclusion
<p>I performed exploratory data analysis, gained insights relevant to the business, developed a sales forecast model with satisfactory performance and presented the results to the CFO in a clear and accessible way through the Telegram bot.</p>
<p>Therefore, I successfully achieved the project's objective, predicting sales for the next six weeks, adding value to the company through a data-based business solution.</p>




## 10. Next Steps to Improve
<ul>
  <li> Investigate model underperformance in specific stores and resolve identified issues. </li>

  <li> Develop a project to predict the number of customers and incorporate this variable into the model, as sales and the number of customers showed a significant correlation. </li>

  <li> Build a model retraining pipeline. </li>
</ul>
