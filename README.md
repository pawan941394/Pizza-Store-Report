<h4 align="left">It's an Data Analysis Project where I have developed a Complete "Pizza-Store-Report" With the SQl and Tableau .</h4>

###

<h6 align="left">We have a data base for this project which i have uploaded . I have used this data base for Analysis .</h6>

###

<p align="left">First I have analysis all results in SQL --<br>Results of analysis are as follows.</p>

###

<p align="left">1.  Find Total Revenue  --</p>

```select sum(total_price) as Total_revenue from pizza_sales ;```

###

<p align="left">2. Find the average order value --</p>

```select sum(total_price)/ count(distinct order_id)  as Average_order_value from pizza_sales;```
###

<p align="left">3. Total Pizza Sold --</p>

```select sum(quantity) as Total_Pizza_Sold from pizza_sales;```
###

<p align="left">4.  Total Orders --</p>

```select count(distinct order_id) as Total_Order from pizza_sales;```
###

<p align="left">5. Average order quantity --</p>

```select sum(quantity) / count(distinct order_id)  as Total_Order from pizza_sales;```
###

<p align="left">6.  Hourly trend for total pizza sold --</p>

```select datepart(Hour, order_time) as order_hour , sum(quantity) AS ordered_quantity from pizza_sales group by datepart(Hour, order_time)  order by datepart(Hour, order_time) ;```
###

<p align="left">7.  Weekly trend for total orders --</p>

```select datepart(iso_week , order_date) as week_number , Year(order_date) as Order_year, count(distinct order_id) as Total_orders from pizza_sales group by datepart(ISO_WEEK, order_date) , year(order_date) order by DATEPART(iso_week, order_date) , year(order_date);```
###

<p align="left">8.  % of sales by pizza category --</p>

```select pizza_category ,cast(sum(total_price)as decimal(10,2))as Total_sale, cast((sum(total_price)*100 ) / (select sum(total_price) from pizza_sales ) as decimal (10, 2)) as Precent_of_total from pizza_sales group by pizza_category ;```
###

<p align="left">9.  % of pizza sales by pizza size  --</p>

```select pizza_size ,cast(sum(total_price)as decimal(10,2))as Total_sale, cast((sum(total_price)*100 ) / (select sum(total_price) from pizza_sales ) as decimal (10, 2)) as Precent_of_total from pizza_sales group by pizza_size;```
###

<p align="left">10.  Total pizzas sold by pizza category  --</p>

```select pizza_category, sum(quantity) as Total_Quantity_sold from pizza_sales group by pizza_category order by Total_Quantity_sold desc;	```
###

<p align="left">11.  Top 5 pizzas by revenue  --</p>

```select  Top 5  pizza_name , sum(total_price) as Total_revenue from pizza_sales group by pizza_name order by Total_revenue desc;```
###

<p align="left">12. Bottom 5 pizzas by revenue   --</p>

```select  Top 5  pizza_name , sum(total_price) as Total_revenue from pizza_sales group by pizza_name order by Total_revenue ;```
###

<p align="left">13.  Bottom 5  pizza sales by quantity --</p>

```select  Top 5  pizza_name , sum(quantity) as Total_revenue from pizza_sales group by pizza_name	order by Total_revenue ;```
###

<p align="left">14.  Top 5  pizza sales by quantity --</p>

```select  Top 5  pizza_name , sum(quantity) as Total_revenue from pizza_sales group by pizza_name order by Total_revenue  desc;```
###

<p align="left">15.  Top 5  pizza sales by orders --</p>

```select  Top 5  pizza_name , count(distinct order_id) as Total_orders from pizza_sales group by pizza_name order by Total_orders  desc;```
###

<p align="left">16.  Bottom 5  pizza sales by orders  --</p>

```select  Top 5  pizza_name , count(distinct order_id) as Total_orders from pizza_sales group by pizza_name order by Total_orders  ;```
###
