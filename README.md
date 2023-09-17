<h4 align="left">It's an Data Analysis Project where I have developed a Complete "Pizza-Store-Report" With the SQl and Tableau .</h4>

###

<h6 align="left">We have a data base for this project which i have uploaded . I have used this data base for Analysis .</h6>

###

<p align="left">First I have analysis all results in SQL --<br><br>Results of analysis are as follows.</p>

###

<p align="left">1.  Find Total Revenue  --</p>

```select sum(total_price) as Total_revenue from pizza_sales ;```

<p align="left">Results  --</p>

![q1](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/1f0b7926-e657-42a1-95c7-cfa081584b63)

###

<p align="left">2. Find the average order value --</p>

```select sum(total_price)/ count(distinct order_id)  as Average_order_value from pizza_sales;```

<p align="left">Results  --</p>

![q2](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/2dc4e279-a486-430c-a2db-54a15db781d8)


###

<p align="left">3. Total Pizza Sold --</p>

```select sum(quantity) as Total_Pizza_Sold from pizza_sales;```

<p align="left">Results  --</p>

![s3](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/1baa5fcc-c385-4124-8e95-9b3ece71f199)

###

<p align="left">4.  Total Orders --</p>

```select count(distinct order_id) as Total_Order from pizza_sales;```

<p align="left">Results  --</p>

![q4](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/2e7162af-e145-4695-98c2-9691486895cf)


###

<p align="left">5. Average order quantity --</p>

```select sum(quantity) / count(distinct order_id)  as Total_Order from pizza_sales;```

<p align="left">Results  --</p>

![q5](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/378ccfcf-37b4-4a75-97c1-dee9b4653188)


###

<p align="left">6.  Hourly trend for total pizza sold --</p>

```select datepart(Hour, order_time) as order_hour , sum(quantity) AS ordered_quantity from pizza_sales group by datepart(Hour, order_time)  order by datepart(Hour, order_time) ;```

<p align="left">Results  --</p>

![q6](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/8a099717-52b7-4730-a9a7-9e5c4125beb6)

###

<p align="left">7.  Weekly trend for total orders --</p>

```select datepart(iso_week , order_date) as week_number , Year(order_date) as Order_year, count(distinct order_id) as Total_orders from pizza_sales group by datepart(ISO_WEEK, order_date) , year(order_date) order by DATEPART(iso_week, order_date) , year(order_date);```

<p align="left">Results  --</p>

![q7](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/9e072ab1-444d-4d70-bac2-084b38bafeb1)

###

<p align="left">8.  % of sales by pizza category --</p>

```select pizza_category ,cast(sum(total_price)as decimal(10,2))as Total_sale, cast((sum(total_price)*100 ) / (select sum(total_price) from pizza_sales ) as decimal (10, 2)) as Precent_of_total from pizza_sales group by pizza_category ;```

<p align="left">Results  --</p>

![q8](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/efcb8903-811f-4b9a-9f9d-fec0e78fe890)

###

<p align="left">9.  % of pizza sales by pizza size  --</p>

```select pizza_size ,cast(sum(total_price)as decimal(10,2))as Total_sale, cast((sum(total_price)*100 ) / (select sum(total_price) from pizza_sales ) as decimal (10, 2)) as Precent_of_total from pizza_sales group by pizza_size;```

<p align="left">Results  --</p>

![q10](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/e28a67d4-64cb-41c0-943c-4e7894cdbb0e)

###

<p align="left">10.  Total pizzas sold by pizza category  --</p>

```select pizza_category, sum(quantity) as Total_Quantity_sold from pizza_sales group by pizza_category order by Total_Quantity_sold desc;	```

<p align="left">Results  --</p>

![q11](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/4884fc01-3c91-4717-b97c-dad035ff23c7)

###

<p align="left">11.  Top 5 pizzas by revenue  --</p>

```select  Top 5  pizza_name , sum(total_price) as Total_revenue from pizza_sales group by pizza_name order by Total_revenue desc;```

<p align="left">Results  --</p>

![q12](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/f5451a20-d77c-498d-b147-86ba57053e6a)

###

<p align="left">12. Bottom 5 pizzas by revenue   --</p>

```select  Top 5  pizza_name , sum(total_price) as Total_revenue from pizza_sales group by pizza_name order by Total_revenue ;```

<p align="left">Results  --</p>

![Q13](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/558e457e-489a-4c95-8129-3877c61f2508)

###

<p align="left">13.  Bottom 5  pizza sales by quantity --</p>

```select  Top 5  pizza_name , sum(quantity) as Total_revenue from pizza_sales group by pizza_name	order by Total_revenue ;```

<p align="left">Results  --</p>

![q14](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/48f791d7-410a-450c-baf3-ea69d4e7237d)

###

<p align="left">14.  Top 5  pizza sales by quantity --</p>

```select  Top 5  pizza_name , sum(quantity) as Total_revenue from pizza_sales group by pizza_name order by Total_revenue  desc;```

<p align="left">Results  --</p>

![q15](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/9f4f44fe-b902-46bb-8387-05f79bd0bd77)

###

<p align="left">15.  Top 5  pizza sales by orders --</p>

```select  Top 5  pizza_name , count(distinct order_id) as Total_orders from pizza_sales group by pizza_name order by Total_orders  desc;```

<p align="left">Results  --</p>

![Q16](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/acd757d9-3a7c-4686-bba7-b94148e89fda)

###

<p align="left">16.  Bottom 5  pizza sales by orders  --</p>

```select  Top 5  pizza_name , count(distinct order_id) as Total_orders from pizza_sales group by pizza_name order by Total_orders  ;```

<p align="left">Results  --</p>

![q17](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/4b07f7c3-cecf-43cd-b0ca-41ed09f57f86)


<p align="left">Second I have analysis all results in Tableau --<br>Results of analysis are as follows.</p>

###

<p align="left">1.  % Sales for Pizza Size --</p>

<p align="left">Results  --</p>

![% Sales for pizza size](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/85d6088e-ded3-4604-a611-2a81d08f1338)


###

<p align="left">2. % Sales Of Pizzas --</p>

<p align="left">Results  --</p>

![% sales of pizzas](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/717deceb-9160-4d16-a2c1-6d4c9a248f8e)


###

<p align="left">3. Bottom 5 Pizza by revenue --</p>

<p align="left">Results  --</p>

![bottom 5 pizza by revenue](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/63e7e750-9880-4184-a2a3-70cda4e3d628)

###

<p align="left">4. Bottom 5 pizzas by Category --</p>

<p align="left">Results  --</p>

![bottom 5 pizzas by category](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/0eb13f64-6e3d-4372-8c8b-8837c3c32dc4)

###

<p align="left">5. Bottom 5 Pizzas by total Pizza Sold --</p>

<p align="left">Results  --</p>

![bottom 5 pizzas by total pizza sold](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/012c9349-ac1f-49fd-b828-7415b996332a)


###


###

<p align="left">6.  Date Range --</p>

<p align="left">Results  --</p>

![Date Range](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/79b3cdaa-ab90-4baa-baee-98748828d68f)


###

<p align="left">7.  Hourly Trend For Pizza --</p>

<p align="left">Results  --</p>

![Hourly Trend For Pizza](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/b31da578-95e1-4be6-a8b9-e20c1f75317e)

###

<p align="left">8.  KPI-Banner --</p>

<p align="left">Results  --</p>

![KPI-Banner1 ](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/30a8b59b-3e5b-4565-8184-da970aa05f6b)

###


###

<p align="left">9.  Top 5  Pizzas by Quantity  --</p>

<p align="left">Results  --</p>

![top 5  pizzas by quantity](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/e9146094-eb8e-4341-9203-f79aa2ccc5fd)

###

<p align="left">10. Top 5 Pizzas by revnue  --</p>

<p align="left">Results  --</p>

![Top 5 pizzas by revnue](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/780de256-34ef-4392-9e4e-2c3b50385f7a)

###

<p align="left">11.  Top 5 Pizzas by total Pizza Sold --</p>

<p align="left">Results  --</p>

![top 5 pizzas by total pizza sold](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/a0230195-db66-447e-b442-df3e4c6f0686)

###

<p align="left">12.  Total Pizza And Pizza Sold By Pizza Category --</p>

<p align="left">Results  --</p>

![total pizza and pizza sold by pizza category](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/1ced8421-61f2-4372-9e19-8b06d6ba8bd6)

###


###

<p align="left">13.  Weekly Trend For Pizza --</p>

<p align="left">Results  --</p>

![Weekly Trend for pizza](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/d329cfca-5003-4eec-aee0-34c4ade44a98)



<h3 align="left">Let's Create Dashbord Now --</h2>

<p align="left">Dashbord 1  --</p>

![MainDashbord](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/41058d17-985a-4963-b95e-f7e7b2917244)


<p align="left">Dashbord 2 -- After Click On Best/Worst Sellers Button  --</p>

![dashbord 2](https://github.com/pawan941394/Pizza-Store-Report/assets/63099276/fbce0b69-0f00-4857-a89e-00eb5050b9b8)


###
