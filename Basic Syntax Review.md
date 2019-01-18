select column1, column2 from tabl

```sql
select col1, col2, col3 from tablename;
```

tuple can have many duplicates what to eleminate duplicate use

```sql
select distinct col1 from tablename;
select count(distinct) col1 from tablename;
```

## Where Clause

```sql
select * from customers where country='Mexico';
select * from customers where customerid=1; --notice the equal sign is '=' not '=='
```

## And, or and not operators

```sql
SELECT col1, col2 FROM table_name where con1 and cond2;
select col1, col2 from table_name where con2 and con 3;
select * from customers where country='Germany' and city='berlin';
select * from customers where not country='Germany';
select * from customers where country='Germany' and (city='berlin' or city='munchen');
select * from customers where not country='Germany' and not country='USA';
```

## `order by` 

it is used to sort the result

```sql
select * from customers order by country desc;
select * from customers order by country asc, customerName desc; --the one putted at the front has higher order.
```

## Insert

```sql
Insert into customers(CustomerName, ContactName, Address, City, PostalCode, Country) VALUES('Cardinal', 'Tom B erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway');
```

## Null value

A field with a null value is a field with no value, that is left blank during the the table creation

```sql
select column_names from table_name where column_name is null;
select column_names from table_name where column_name is not null;
```

## Update a table

```sql
update Customers
set contactName='Juan' --set is the keyword
where country = 'mexico';
```

## Delete a table

```sql
delete from customers where customername='Alfreds Futterkiste';
```

## Limit a number in the selection process

`ROWNUM` is a special keyword for limiting the number of tuples in the table.

```sql
select column_names from table_name where ROWNUM <= number;
```

## Select min, average, sum, count

```sql
select max(price) as LargestPrice from products;
select avg(price) from prodcuts where conditions;
select sum(column_name) from products where contiditon;
select min(price) as smallestPrice from products;
```

## SQL like operator

like operator is used in a where clause to search for a specified pattern in a column

```sql
select column1, column2 from table_name where columnN like pattern;
select * from customers where customername like '%a';
select * from customers where customername like '%or%';
select * from customers where customername like '_a%'; -- a starts at hte second position
```

## The sql `in` operator

The in operator allows you to specify multiple values in a where caluse. The in operator allows you to specify multiple values in a where clause. It allows you to specify subqueries.

```sql
select * from customers where country in ('Germany', 'France', 'UK');
select * from customers where country not in (select country from suppliers);
```

### BETWEEN with In Example

```sql
select * from products where (Price between 10 and 20) and not categoryID IN (1, 2, 3);
select * from orders where orderDate between '1996-07-01' and '1997-07-31';
```

```sql
select customerName, Address + ', ' + PostalCode + ' ' + City + ', ' + Country as address from customers;
```

## Alias for tables Example

The alias here allows people to join tables without writing lengthy table names.

```sql
select o.orderID, o.orderDate, c.customerName
from customers as c, orders as o
where c.customerName="Around the horn" and c.CustomerID = o.customerID;
```

## Inner Join

A join clause is used to combine row from two or mroe tables.

joining on a specific attribute

```sql
select Orders.orderID, Customers.name, orders.orderDate from orders inner join customers on orders.customerID = customers.customerID;
```

