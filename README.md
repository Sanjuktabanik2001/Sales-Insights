# Sales-Insights

## Power BI Data Analysis Project for Sales Insights

#### PowerPoint Presentation Link:  
https://www.canva.com/design/DAFclgVpJv8/ZtIgfrFH7jaMYBGZ2IFPUw/view?utm_content=DAFclgVpJv8&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton

#### Data Analysis using SQL  
  ##### 1.Show all customer records  
      SELECT * FROM customers;

  ##### 2.Show total number of customers  
      SELECT count(*) FROM customers;

  ##### 3.Show transactions for Chennai market (market code for Bengaluru is Mark006 
      SELECT * FROM transactions where market_code='Mark006';

  ##### 4.Show distrinct product codes that were sold in Bengaluru
         SELECT distinct product_code FROM transactions where market_code='Mark006';

  ##### 5.Show transactions where currency is US dollars  
      SELECT * from transactions where currency="USD"

  ##### 6.Show transactions in 2018 join by date table  
      SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2018;

  ##### 7.Show total revenue in year 2018,  
      SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2018 and transactions.currency="INR\r" or transactions.currency="USD\r";

  ##### 8.Show total revenue in year 2018, February Month,  
      SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2018 and and date.month_name="February" and (transactions.currency="INR\r" or transactions.currency="USD\r");

  ##### 9.Show total revenue in year 2018 in Bengaluru  
      SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2018 and transactions.market_code="Mark006";

#### Data Analysis using Power Bi  
  ##### Formula to create norm_sales_amount column  
      = Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*82.40 else [sales_amount], type any)

## **Power BI User Interface: (Whole Years Report)**
![image](https://user-images.githubusercontent.com/80545634/224071471-1fdc0785-be22-40ed-b43f-b9fbe883724b.png)
<br>
## **Power BI User Interface: (Specific Year 2018 Report)**  
![image](https://user-images.githubusercontent.com/80545634/224076905-100b1b71-8aa8-4bfd-8115-3a5a28230fb9.png)  
<br>
## **Power BI User Interface: (Bengaluru for year 2018 Report)**
![image](https://user-images.githubusercontent.com/80545634/224078365-78cfc02e-7dce-4b81-8a14-8f3151f0b97e.png)


