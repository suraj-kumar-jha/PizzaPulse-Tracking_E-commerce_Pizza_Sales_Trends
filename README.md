
# PizzaPulse: Tracking Pizza Sales Trends -- [E-Commerce Project]
_____________________________________________________


### Tools Used:-
--------------------------

1. Power BI: For data visualization and interactive dashboards.
   
2. MySQL: For database management and data querying.
   
3. MS Excel: For data cleaning and analysis.
   
4. MS Word: For documenting findings and creating reports.

---------------------------
### TABLE OF CONTENTS:-
__________________________

- [KPI'S REQUIREMENT](#kpis-requirement)
- [CHARTS REQUIREMENT](#charts-requirement)
- [PIZZA ANNUAL SALES SQL QUERIES](#pizza-annual-sales-sql-queries)
- [PIZZAS SALES CHARTS](#pizzas-sales-charts)
- [DASHBOARD 1](#dashboard-1)
- [DASHBOARD 2](#dashboard-2)
- [CONCLUSION](#conclusion)
- [IMPROVING SALES AND PROFITABILITY](#improving-sales-and-profitability)


---------------------------
### PROBLEM STATEMENT:-
___________________________

In the competitive pizza industry, understanding customer behavior is crucial for driving sales and enhancing customer satisfaction. The objective of this project is to conduct a comprehensive analysis of sales data to identify customer preferences, peak purchasing times, and other significant patterns. By leveraging data visualization and analytical tools, the company seeks to uncover actionable insights that can inform strategic decisions, optimize business operations, and ultimately boost performance. This analysis aims to provide a clearer understanding of what drives customer purchases, enabling the company to tailor its offerings and marketing efforts more effectively.


----------------------------
### KPI'S REQUIREMENT
----------------------------

#### 1. Total Revenue:- 

=>  The sum of the total price or total sales of all pizza orders.

#### 2. Average Order Value:- 

=>  The average amount spent per order, calculated by dividing the total revenue by the total number of orders.

#### 3. Total Pizzas Sold:- 

=>  The total quantity of pizzas sold.

#### 4. Total Orders:-

=>  The overall number of orders placed.

#### 5. Average Pizzas Per Order:-

=>  The average number of pizzas sold per order, calculated by dividing the total number of pizzas sold by the total number of orders.


----------------------------
### CHARTS REQUIREMENT
----------------------------

We aim to visualize different aspects of our pizza sales data to gain insights and understand key trends effectively. We've outlined the following requirements for creating charts: -

#### 1. Hourly Trend for Total Orders:-

=>  Make a bar chart that shows how many orders we get each hour during a specific time. This helps us see if there are any patterns or changes in order
numbers during different times of the day.

#### 2. Weekly Trend for Total Orders:-
   
=>  Make a line and Area chart that shows how many orders we get each week throughout the year. This helps us see which weeks have the most orders or
when we're busiest.

#### 4. Percentage of Sales by Pizza Category:-

=>  Make a pie chart that shows what Percentage and Total Revenue of our sales come from each type of pizza. This helps us understand which types of pizza are most popular and how much they contribute to our overall sales.

#### 5. Percentage of Sales by Pizza Size:-

=> Make a slider chart that shows the percentage of sales for different pizza sizes. This chart helps us understand what pizza sizes customers prefer and how they affect our sales.

#### 5. Total Orders and Total Pizzas Sold by Pizza Category:-

=> Create a Butterfly chart that compares the total number of pizzas sold and total orders for each pizza category. This chart helps us see how different pizza categories perform in terms of sales.

#### 6. Top 5 Best Sellers by Revenue, Total Quantity, and Total Orders:-

=> Make a bar chart showing the top 5 best-selling pizzas based on revenue, total quantity sold, and total orders placed. This chart helps us identify the most popular pizza options.

#### 7. Bottom 5 Best Sellers by Revenue, Total Quantity, and Total Orders:-

=> Create a bar chart displaying the bottom 5 worst-selling pizzas based on revenue, total quantity sold, and total orders placed. This chart helps us
identify underperforming or less popular pizza options.

-------------------------------------------------
### PIZZA ANNUAL SALES SQL QUERIES
-------------------------------------------------

#### KPI’S VALUES:

#### 1. TOTAL REVENUE:-
```
SELECT ROUND(SUM (total_price)) AS TOTAL_REVENUE FROM pizza_sales;
```
<img width="150" alt="Screenshot 2024-05-24 at 12 43 23 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/bec7326a-675e-457d-ba31-1c238e744dc1">


#### 2. TOTAL ORDERS:-
```
SELECT COUNT(DISTINCT(order_id )) AS TOTAL_ORDERS FROM pizza_sales;
```
<img width="154" alt="Screenshot 2024-05-24 at 12 56 43 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/73846d92-0f3f-478c-a3ef-7a18212762d4">

#### 3. TOTAL PIZZAS SOLD:-
```
SELECT SUM(quantity) AS TOTAL_PIZZAS_SOLD FROM pizza_sales;
```
<img width="162" alt="Screenshot 2024-05-24 at 12 57 47 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/22f05392-8609-4331-8f46-08548f0ff339">


#### 4. AVERAGE ORDER VALUE:-
```
SELECT ROUND((SUM(total_price) / COUNT(DISTINCT(order_id ))) ,2) AS
AVERAGE_ORDER_VALUE FROM pizza_sales;
```
<img width="174" alt="Screenshot 2024-05-24 at 12 58 42 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/dd537084-f8f1-4e8b-bee4-d1545c9c7591">


#### 5. AVERAGE PIZZA PER ORDER:-
```
SELECT ROUND(SUM(quantity ) / COUNT(DISTINCT( order_id )) ,2) AS
AVERAGE_PIZZA_PER_ORDER FROM pizza_sales
```
<img width="183" alt="Screenshot 2024-05-24 at 12 59 34 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/c2e6a9b7-bde8-474a-a9ec-20250ab5bb87">

-------------------------

<img width="1092" alt="Screenshot 2024-05-24 at 2 06 15 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/ac1b8525-8a71-4dda-94ef-8a116801709c">

-------------------------------------------------
### PIZZAS SALES CHARTS
-------------------------------------------------

#### 1. Hourly Trend for Total Pizzas Sold:-
```
SELECT HOUR(order_time ) AS HOURS , SUM( quantity ) AS TOTAL_PIZZAS_SOLD
FROM pizza_sales
GROUP BY HOURS
ORDER BY TOTAL_PIZZAS_SOLD DESC;
```
<img width="266" alt="Screenshot 2024-05-24 at 1 02 42 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/5413c2cc-87d6-46be-beda-45ed32097366">

<img width="552" alt="Screenshot 2024-05-24 at 1 51 19 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/985f7415-4002-4503-afc1-073bcb2ba3e5">


#### 2. Weekly Trend for Total Orders:-
```
SELECT DAYNAME( order_date ) AS WEEK_NAME,COUNT(DISTINCT(order_id)) AS
TOTAL_PIZZAS_ORDER
FROM pizza_sales GROUP
BY WEEK_NAME
ORDER BY TOTAL_PIZZAS_ORDER DESC;
```
<img width="331" alt="Screenshot 2024-05-24 at 1 07 09 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/2b2bd529-f58f-4880-8521-69abcb027d4a">

<img width="538" alt="Screenshot 2024-05-24 at 1 53 24 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/4dd7ecbb-d8ed-4b54-b454-1827234392c0">


#### 3. Percentage of Sales by Pizza Category:-
```
SELECT (pizza_category) AS PIZZA_CATEGORY,
ROUND((SUM(total_price )*100 ) / (SELECT SUM( total_price ) FROM pizza_sales) , 1)AS
TOTAL_PIZZAS_SALES_PCT,
ROUND(SUM(total_price )) AS TOTAL_REVENUE
FROM pizza_sales
GROUP BY PIZZA_CATEGORY
ORDER BY TOTAL_PIZZAS_SALES_PCT DESC;
```
<img width="435" alt="Screenshot 2024-05-24 at 1 09 03 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/d82af1d1-710d-4c28-adb0-7c1e9509dd54">

<img width="353" alt="Screenshot 2024-05-24 at 1 55 11 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/2ab68bfd-45bb-45a3-9514-6dda7cfcf922">


#### 4. Percentage of Sales by Pizza SIZE:-
```
SELECT ( pizza_size) AS PIZZA_SIZE,
ROUND((SUM( total_price )*100 ) / (SELECT SUM( total_price ) FROM pizza_sales) , 1)AS
TOTAL_PIZZAS_SALES_PCT,
ROUND(SUM(total_price )) AS TOTAL_REVENUE
FROM pizza_sales
GROUP BY PIZZA_SIZE
ORDER BY TOTAL_PIZZAS_SALES_PCT DESC;
```
<img width="464" alt="Screenshot 2024-05-24 at 1 10 24 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/d61e8bda-74e3-4460-b1e6-6e17fdbeb744">

<img width="358" alt="Screenshot 2024-05-24 at 1 58 10 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/bea1e68b-8e22-4df8-bf7b-65b227af3465">


#### 5. Total Orders and Total Pizza’s Sold by Category:-
```
SELECT pizza_category AS PIZZA_CATEGORY,
ROUND(SUM( quantity )) AS TOTAL_QUANTITY,
COUNT(DISTINCT( order_id )) AS TOTAL_ORDERS
FROM pizza_sales
GROUP BY PIZZA_CATEGORY
ORDER BY TOTAL_ORDERS DESC;
```
<img width="467" alt="Screenshot 2024-05-24 at 1 12 37 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/72d1e7db-f6b7-4dd4-b406-c778a55a74ae">

<img width="370" alt="Screenshot 2024-05-24 at 2 10 25 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/480e7e11-ce5c-409e-b69e-068a8074d089">



#### 6. Total 5 Best Sellers by Total Orders:-
```
SELECT pizza_name AS PIZZA_NAME,
COUNT(DISTINCT(order_id)) AS TOTAL_ORDERS
FROM pizza_sales GROUP BY
PIZZA_NAME
ORDER BY TOTAL_ORDERS DESC
LIMIT 5;
```
<img width="396" alt="Screenshot 2024-05-24 at 1 14 15 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/29712b49-1221-4dd2-9805-848931d45233">

<img width="357" alt="Screenshot 2024-05-24 at 2 03 54 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/ae0c968b-79d8-400b-b3dd-9f9cbf947fe7">


#### 7. Total 5 Worst Sellers by Total Orders:-
```
SELECT pizza_name AS PIZZA_NAME,
COUNT(DISTINCT(order_id)) AS TOTAL_ORDERS
FROM pizza_sales GROUP BY
PIZZA_NAME
ORDER BY TOTAL_ORDERS
LIMIT 5;
```
<img width="399" alt="Screenshot 2024-05-24 at 1 16 06 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/dc25950b-c301-4553-ad7a-98dbd583edae">

<img width="355" alt="Screenshot 2024-05-24 at 1 45 35 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/b4dd926b-611e-43a0-93af-87e488c07cde">


#### 8. Total 5 Best Sellers by Total Pizzas Sold:-
```
SELECT pizza_name AS PIZZA_NAME,
SUM(quantity) AS TOTAL_PIZZAS_SOLD
FROM pizza_sales
GROUP BY PIZZA_NAME
ORDER BY TOTAL_PIZZAS_SOLD DESC
LIMIT 5;
```
<img width="419" alt="Screenshot 2024-05-24 at 1 17 23 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/d8c92944-3ef6-4c25-a7ab-7f25f55972ed">

<img width="359" alt="Screenshot 2024-05-24 at 2 12 35 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/bd1e8318-0335-481e-9ad9-e1eabed41c22">


#### 9. Total 5 Worst Sellers by Total Pizzas Sold:-
```
SELECT pizza_name AS PIZZA_NAME,
SUM(quantity) AS TOTAL_PIZZAS_SOLDFROM
pizza_sales
GROUP BY PIZZA_NAME ORDER BY
TOTAL_PIZZAS_SOLD
LIMIT 5;
```
<img width="439" alt="Screenshot 2024-05-24 at 1 18 34 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/0ea335eb-e99b-48a0-b187-96984b51f609">

<img width="356" alt="Screenshot 2024-05-24 at 2 15 45 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/f9e93004-545d-49f4-aaff-e9f5fe8bd536">


#### 10. Total 5 Best Sellers by Total Revenue:-
```
SELECT pizza_name AS PIZZA_NAME, ROUND(SUM(total_price)) AS TOTAL_REVENUE
FROM pizza_sales
GROUP BY PIZZA_NAME
ORDER BY TOTAL_REVENUE DESC
LIMIT 5;
```
<img width="431" alt="Screenshot 2024-05-24 at 1 20 02 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/b27fdf20-b820-4f3e-ba7d-1eabd0e6afc8">

<img width="369" alt="Screenshot 2024-05-24 at 2 17 10 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/bf1c9420-5a3e-4e94-8887-8e42a9ad688a">


#### 11. Total 5 Worst Sellers by Total Revenue:-
```
SELECT pizza_name AS PIZZA_NAME, ROUND(SUM(total_price)) AS TOTAL_REVENUE
FROM pizza_sales
GROUP BY PIZZA_NAME
ORDER BY TOTAL_REVENUE
LIMIT 5;
```
<img width="409" alt="Screenshot 2024-05-24 at 1 21 17 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/c8c954f8-83ce-456d-ae55-349b82ae7520">

<img width="365" alt="Screenshot 2024-05-24 at 2 18 11 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/b9197aff-6892-4c6b-a79f-794d28bc84ec">


-------------------------------------------------
### Dashboard 1
-------------------------------------------------

<img width="1309" alt="Screenshot 2024-05-24 at 2 19 50 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/7312b70c-db27-4546-bbc8-4ef644ad7170">



-------------------------------------------------
### Dashboard 2
-------------------------------------------------

<img width="1308" alt="Screenshot 2024-05-24 at 2 22 19 PM" src="https://github.com/suraj-kumar-jha/PizzaPulse-Tracking_E-commerce_Pizza_Sales_Trends/assets/155900363/05a50258-87ab-4e5f-a734-3564ff2ad3cd">


-------------------------------------------------
### Conclusion
-------------------------------------------------

• Peak operational hours are observed during lunchtime and evenings, with Fridays emerging as the busiest day of the week.

• The Classic Category and Large-sized pizzas demonstrate the highest sales volume, indicating their popularity among customers.

• The Thai Chicken Pizza leads in revenue, suggesting its strong appeal to customers willing to spend more.

• The Classic Deluxe Pizza ranks highest in quantity sold and orders, highlighting its consistent popularity among customers.

• The Brie Carre Pizza consistently underperforms, indicating a potential need for re-evaluation or improvement in its presentation or marketing strategy.

• Optimizing operations around peak hours and popular items while addressing underperforming products could significantly enhance overall
business performance and profitability.

-------------------------------------------------
### Improving Sales and Profitability
-------------------------------------------------

• Implement targeted marketing campaigns during peak hours and on Fridays to capitalize on increased customer traffic.

• Introduce promotional offers or discounts on Classic Category and Large-sized pizzas to incentivize purchases and boost sales volume.

• Enhance the presentation and promotion of the Thai Chicken Pizza to further capitalize on its revenue-generating potential.

• Consider refining the recipe or marketing strategy for the underperforming Brie Carre Pizza to improve its appeal to customers.

• Optimize staffing levels and operational processes during peak hours to ensure efficient service delivery and customer satisfaction.

• Continuously monitor sales data and customer feedback to identify trends, preferences, and areas for further improvement in sales and profitability
strategies.
