
# pizza sales dashboard

### Dashboard Link :https://app.powerbi.com/links/ugtE45SmrF?ctid=3e0c3739-b6da-4ac6-98f8-648ce617acdd&pbi_source=linkShare

## Problem Statement

This dashboard helps gains insight of a business performance for pizza shop,and help the business understand their customers better and improve sales. It helps the business know if their customers are satisfied with their services. Through the top 5 and bottom 5 sales category , they get to know the average amount spent per order, & thus they can improve their services by identifying  the downlines . It also lets them know the average number of pizza sold per order  & and the average amount sold per order, thus  by using this dashboard they have identified this problem, they can further work on factors responsible for the bottom 5 pizza category.

Since, the thai chicken pizza contributes to the maximum revenue and maximum total order and the brie carre pizza contributues the minimum revenue and minimum total order thus they must work on improving their worse selling product or taking it out the menu . 

Also since the top 5 best selling pizza based on revenue is not the same category as the top 5 best selling based on quantity thus they must try to reduce the quantity they make the bottom seller based on quantity.


### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset from SQL sever.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values were present .
- Step 5 : For calculating the total revenue, null values were not taken into account as they are no null values are in this column(i.e select sum(total_price) As total_revenue from pizza_sales) 
- Step 6 : thirteen other SQL queries where carried out to determine the total pizza sold, average order value,daily trend for total orders,Average pizza per order,Monthly trend for total order, Percentage of sales by pizza category,Percentage of sales by pizza size,top 5 pizza by revenue,bottom 5 pizza by revenue ,top 5 pizza by quantity,top 5 pizza by order ,
 In the report view, under the view tab, theme was selected.

 ![image](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/b741101a-b805-430e-a4e8-7272f25437ce)
 
- Step 7 : Since the data contains various pizza category, thus in order to represent them in a chart , a new visual was added using the three ellipses in the visualizations pane in report view. 
- Step 8 : Visual filters (Slicers) were added for two fields named "order date", "pizza category".
- Step 9 : five card visuals were added to the canvas, one representing daily trends for total order, monthly trends for total orders, percentage of sales by pizza category, percentage of sales by pizza size & total pizza sold by pizza category.

- Step 10 : A column chart was also added to the report design area representing the daily trends for total orders .
- Step 11 : a line chart was added to the report design area reprsenting the monthly trends for total order

- Step 12 : In the report view, by the left hand side of the dashboard, two text boxes were added to the canvas, in one of them name of the sales performance & in the other one busiest days.
- Step 13 : In the report view, under the insert tab, using shapes option from elements group a rectangle was inserted & similarly using image option company's logo was added to the report design area. 
- Step 14 : Calculated column was created in which, the month name was seprated from the month number.

for creating new column following DAX expression was written;
       
        
        Order day = UPPER(LEFT(pizza_sales[Day Name], 3)),
        
       Order month = UPPER(LEFT(pizza_sales[Month Name], 3)),
      
Snap of new calculated column ,

![image](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/24729cc5-0b27-4310-a767-255f9029c1db)

![image](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/a867ca03-4514-493f-849d-dfbc67cb1cc7)
        
- Step 15 : New measure was created to find total revenue.

Following DAX expression was written for the same,
        
                total revenue = COUNT(total_price)
        
A card visual was used to represent total revenue.

![image](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/3aae25ca-db9f-40b3-8cfe-288bb5eee818)

        
 - Step 16 : New measure was created to find  total pizza sold ,
 
 Following DAX expression was written to find total pizza sold,
 
    total pizza sold = sum(pizza_sales[quantity]))
 
 A card visual was used to represent this .
 
 ![image](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/b38b2aa7-c951-4706-b1cb-d0ec0cab378d)
 
 - Step 17 : New measure was created to calculate total order & a card visual was used to represent total order.

 ![image](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/213e32b3-4e57-4a42-a4de-dbdac85e4d0e)

 
 Following DAX expression was written to find total order,
 
         total orders = DISTINCTCOUNT(pizza_sales[order_id])
    
A card visual was used to represent the total order.
 
 
 ![image](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/213e32b3-4e57-4a42-a4de-dbdac85e4d0e)

step 18: New measure was created to calculate average order value  

Following DAX expression was written to find total order,
avg order value = [total revenue]/[total orders]

A card visual was used to represent the average order value 

![image](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/a99d8666-6c88-45f0-bcb3-9bd7a7eafa43)

step 19:New measure was created to calculate average pizza per order 

Following DAX expression was written to find the average pizza per order

avg pizza per orders = [total pizza sold]/[total orders]

A card visual was used to represent the average pizza per order

![image](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/2e91a9be-4300-40ad-a89b-8cf6b59fa082)

 
 - Step 20 :  another report page was created to show the top 5 bestseller and bottom 5 sellers 

 step 21:  In the report view, by the left hand side of the dashboard, two text boxes were added to the canvas, in one of them name of the bestseller & in the other one worstsellers.

![image](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/85b22b08-171e-4066-a828-b6d5ed5008f8)
 
 step 22: a stacked bar chart was added to the report design area reprsenting the top 5 by revenue, top 5 by pizza quntity, top 5 by total order, bottom 5 by revenue, bottom 5 by pizza quantity and botom 5 by total order respectfully

 ![image](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/33a97054-fee5-459d-bcb8-7a979cac45ab)

 The report was then published to Power BI Service.
 
 
![publish massage](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/74b233a8-029e-473e-9fb2-c726f291d191)
# Snapshot of Dashboard (Power BI Service)

![dashboard upload](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/60fabcf1-855d-4450-afd6-d1002295dcc4)


 
 # Report Snapshot (Power BI DESKTOP)

 
![dashboard upload](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/a9a7f550-a342-4b32-83bf-6e369e32c0bb)

# Insights

A single page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard; from SQL queries

1.	Total Revenue

select sum(total_price) As total_revenue from pizza_sales

![image](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/5449b8c7-ffbd-4ad1-8467-bf56257ca677)
	






2.	Average order value

select sum(total_price) / count(DISTINCT order_id) as avg_order_value from pizza_sales

 ![image](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/9a52ef2a-b5c8-46fc-b547-2049cf96dfe5)


3.	Total pizza sold

select sum(quantity) as total_pizza_sold from pizza_sales

![image](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/7659d1bf-d57f-4d74-9b08-a9c50ae2e545)
 

4.	Total orders

select count(DISTINCT order_id) as total_orders from pizza_sales

 ![image](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/58a54b9c-91b9-44f6-8446-001dabd68c87)



5.	Average pizza per order 
select cast(cast(sum(quantity) as decimal(10,2)) /
cast(count(distinct order_id) as decimal(10,2)) as decimal(10,2)) as avg_pizzas_per_order
from pizza_sales

![image](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/2751d42f-b0d7-4971-af8f-dbbe93ea5fb6)
 

6.daily trend for total orders
select datename(DW, order_date) as order_day, count(distinct order_id) as total_order from pizza_sales
group by datename(DW, order_date)

![image](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/550a81d5-16fb-4548-90b0-bc3bede15609)

 


7.Monthly trend for total order
select datename(month, order_date) as month_name, count(distinct order_id) as total_orders from pizza_sales group by datename(month, order_date)
order by total_orders desc

![image](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/ddd9b38a-70bb-4e0f-b043-2b9dc346130b)
 


8.Percentage of sales by pizza category
select pizza_category, sum(total_price) as total_sales, sum(total_price) * 100/ (select sum(total_price) from pizza_sales where month(order_date) = 1) as PCT
from pizza_sales 
where month(order_date) = 1
group by pizza_category

![image](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/16533520-aa5d-4e9d-b03c-1244b132f452)
 

9.Percentage of sales by pizza size:
select pizza_size, cast (sum(total_price) as decimal (10,2))as total_sales, cast(sum(total_price) * 100/
(select sum(total_price) from pizza_sales) as decimal(10,2)) as PCT
from pizza_sales 
where datepart(quarter, order_date) = 1
group by pizza_size
order by PCT desc

 ![image](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/a4eb19c0-6f14-4562-a7f1-b12c53b5994f)



10.top 5 pizza by revenue 

 select  top 5 pizza_name, sum(total_price) as total_revenue from pizza_sales
group by pizza_name 
order by total_revenue desc

 
![image](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/7f284a99-57e3-4e31-83d5-7ebeff6b78a9)


11.bottom 5 pizza by revenue 

select  top 5 pizza_name, sum(total_price) as total_revenue from pizza_sales
group by pizza_name 
order by total_revenue asc

 ![image](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/6b63cdc1-73d2-4fd1-9a27-8bcfa3377ad9)

13. top 5 pizza by quantity
select  top 5 pizza_name, sum(quantity) as total_quantity from pizza_sales
group by pizza_name 
order by total_quantity desc
 
![image](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/920af4ee-2d59-4e8b-8c6d-74ef14d118b4)

14. top 5 pizza by order 
select  top 5 pizza_name, count(distinct order_id) as total_orders from pizza_sales
group by pizza_name 
order by total_orders

![image](https://github.com/vanessaBaj/pizzasalesreport_vanessabaj.github.io/assets/170100152/32f6571d-c708-4e52-9a97-791b0ac68c2d)
 
