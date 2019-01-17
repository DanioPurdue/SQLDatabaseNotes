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

