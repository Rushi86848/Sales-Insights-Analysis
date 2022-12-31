# Sales-Insights-Analysis

Project is based on a computer hardware business which is facing challenges in dynamically changing market.I have build a power BI dashboard that can give real time sales insights. 

I have used mysql database to analyse this database and than hook it up with power BI.This database has all sales transactions, customers, products and markets information. In power BI i have performd ETL and data cleaning operations to build a powerful dashboard that can help to generate sales insights on hardware business. 


## Insides using SQL Queris

1.Show all customer records
```bash
SELECT * FROM customers;
```
2.Show total number of customers
```bash
SELECT count(*) FROM customers;
```
3.Show transactions for Chennai market (market code for chennai is Mark001
```bash
SELECT * FROM transactions where market_code='Mark001';
```
4.Show distrinct product codes that were sold in chennai
```bash
SELECT distinct product_code FROM transactions where market_code='Mark001';
```
5.Show transactions where currency is US dollars
```bash
SELECT * from transactions where currency="USD"
```
6.Show transactions in 2020 join by date table
```bash
SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;
```
7.Show total revenue in year 2020,
```bash
SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";
```
8.Show total revenue in year 2020, January Month,
```bash
SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");
```
9.Show total revenue in year 2020 in Chennai
```bash
SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.market_code="Mark001";
```

## power BI Desktop Report
### Home Page:

![Screenshot_20221231_083900](https://user-images.githubusercontent.com/120455099/210141334-31f7c9b9-5f67-4cab-a3c8-61f9b90dd70f.png)

### Revenue Analysis:

![Screenshot_20221231_083941](https://user-images.githubusercontent.com/120455099/210141451-44d34679-b140-4480-8b9b-211f5350175f.png)

### Profit Analysis:

![Screenshot_20221231_084021](https://user-images.githubusercontent.com/120455099/210141456-633c999d-9f45-4d7c-bcd7-0da26c48a4d8.png)

### Performance Analysis:

![Screenshot_20221231_084117](https://user-images.githubusercontent.com/120455099/210141459-c76b32a8-3801-40df-a7a2-79069378f680.png)
