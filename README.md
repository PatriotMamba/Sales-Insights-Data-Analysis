# Sales-Insights-Data-Analysis
## Instructions to setup mysql on your local computer
1. Follow step in this video to install mysql on your local computer https://www.youtube.com/watch?v=WuBcTJnIuzo
2. SQL database dump is in db_dump.sql file above. Download db_dump.sql file to your local computer and import it as per instructions given in the tutorial video
## Data Analysis Using SQL
1. Show all customer records

2. SELECT * FROM customers;

3. Show total number of customers

4. SELECT count(*) FROM customers;

5. Show transactions for Chennai market (market code for chennai is Mark001

6. SELECT * FROM transactions where market_code='Mark001';

7. Show distrinct product codes that were sold in chennai

8. SELECT distinct product_code FROM transactions where market_code='Mark001';

9. Show transactions where currency is US dollars

10. SELECT * from transactions where currency="USD"

11. Show transactions in 2020 join by date table

12. SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;

13. Show total revenue in year 2020,

14. SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";

15. Show total revenue in year 2020, January Month,

16. SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");

17. Show total revenue in year 2020 in Chennai

18. SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.market_code="Mark001";
# Data Analysis Using Power BI
1. Formula to create norm_amount column
= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)
