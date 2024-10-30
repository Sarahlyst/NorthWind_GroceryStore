# REPORTS ON GROCERY STORE ANALYSIS (NORTHWIND)
### About
1.1 MySQL
MySQL is a popular open-source Relational Database Management System (RDBMS) that enables efficient storage, organization, and retrieval of data.

Importance in Database Management:
- Data Storage: Securely stores structured and unstructured data.
- Data Retrieval: Efficiently retrieves data using SQL queries.
- Data Security: Supports access control, encryption, and backup/restore.
- Data Integrity: Ensures data consistency and accuracy.
- Scalability: Handles high traffic and large datasets.
#### Grocery Store Analysis
The data consists of 8 different tables which has information on customers, employees, orders, products, shippers and suppliers. Our analysis provides the company the insights they need to make data-based decisions. You can find the attached datasets in this repository.
### Project Overview
The goal of this project is to examine various aspects of a grocery store’s operations to optimize performance, improve customer satisfaction, and increase profitability.
#### Database Structure
The database structure used Relational Database (RDBMS) because the data is stored and organized using tables, rows and columns. 
There were eight tables named:
1. Categories_north
2. Customer_north
3. Orderdetails_north
4. order_north
5. employees_north
6. Suppliers_north
7. Products_north
8. Shippers_north
   
#### Table Structure:
```sql
Create table Categories_north(
CategoryID int (primary key),
CategoryName text, 
Description text, Picture text);

Create table Customer_north(
CustomerID text (primary key),
CompanyName text,ContactName text,
ContactTitle text, Address text, City text,
Region text, PostalCode text, Country text,
Phone text, Fax text, Image text, ImageThumbnail text);

Create table Orderdetails_north(
OrderID int, ProductID int, UnitPrice double,
Quantity int, Discount int);

Create table order_north(
OrderID int, CustomerID text, EmployeeID int,
OrderDate text, RequiredDate text, ShippedDate text,
ShipVia int, Freight double, ShipName text,
ShipAddress text, ShipCity text, ShipRegion text,
ShipPostalCode text, ShipCountry text);

Create table employees_north (
EmployeeID int, LastName text, FirstName text,
Title text, TitleOfCourtesy text, 
BirthDate text, HireDate text,
Address text, City text, Region text,
PostalCode text, Country text, HomePhone text,
Extension int, Photo text, Notes text, ReportsTo text);

Create table Suppliers_north (
SupplierID int, CompanyName text,
ContactName text, ContactTitle text, 
Address text, City text, Region text,
PostalCode text, Country text, Phone text,
Fax text, HomePage text);

Create table Products_north (
ProductID int, ProductName text,
SupplierID int, CategoryID int,
QuantityPerUnit text, UnitPrice double,
UnitsInStock int, UnitsOnOrder int,
ReorderLevel int, Discontinued int);

Create table Shippers_north (
ShipperID int, CompanyName text,
Phonetext);
```

#### Some MySQL queries used to perform analysis in this project
SELECT, WHERE, ORDER BY, AND, OR, LIMIT, INNER JOIN, HAVING, IN, NOT IN, SUM(), MAX(), AVG(), MIN(), LIKE, CREATE DATABASE.

#### Key Concepts Learned:
During the course of this project, I learned more about Joins and Aggregations. The use of joins help me to be able to combine rows from two and more tables based on their related column. E.g.
```sql
select suppliers_north.supplierid,
suppliers_north.companyname,
categories_north.categoryname, 
products_north.productname,
products_north.unitprice
from suppliers_north
join products_north on
suppliers_north.supplierid = products_north.supplierid
join categories_north on
products_north.categoryid = categories_north.categoryid;
```

The use of aggregates function helps to perform calculations on a set of values. E.g.

```sql
select avg(unitprice) as average_price,
min(unitprice) as minimum_price,
max(unitprice) as maximum_price
from orderdetails_north;
```
These concepts help me with the insights I need to make my conclusions and recommendations. 

#### Challenges faced
I faced some challenges with the use of joins and aggregate functions, my queries were giving me errors at first but I was able to overcome it with the help of Meta AI and more research on google. Doing this has broaden my understandings on the topics.
##### The use of some SQL Queries
```sql
select customerid, sum(freight) as sum_of_freight
from orders_north
group by customerid
having sum_of_freight > 200;
```
Select: Retrieves customerid column and sum(freight) column.

Sum: adds up the freight.

Group by: it is used for grouping data, it will group the result above by customerid.

Having: It is used for filtering data, so the result will produce only sum of freight greater than 200.

### Conclusion
I have extensive experience using MySQL, having worked various databases and queries. My expertise include SQL query writing, Joining and Aggregating data, and Data analysis.
Using MySQL, I analyzed the grocery store data to gain insights into customer behavior, sales trends, and product performance. The analysis include Exploratory data analysis, Product performance analysis, Sales trend analysis, Customer segmentation.
By leveraging MySQL and data analysis techniques, I was able to extract valuable insights from the grocery store data, providing actionable recommendations for business improvement.
