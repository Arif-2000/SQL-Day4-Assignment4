# SQL-Day4-Assignment4

create table books
(
id numeric(4) primary key,
title varchar(30),
author varchar(30),
isbn numeric(20) unique,
published_date datetime
)

insert into books(id,title,author,isbn,published_date) values(1,'My First SQL book','Mary Parker',981483029127,'2012-02-22 12:08:17'),
(2,'My Second SQL book','John Mayer',857300923713,'1972-07-03 09:22:45'),
(3,'My Third SQL book','Cary Flint',523120967812,'2015-10-18 14:05:44')

select * from books

create table reviews
(
id numeric(4) references books(id),
bookid numeric(4),
reviewer_name varchar(30),
content varchar(30),
rating numeric(4),
published_date datetime
)

insert into reviews(id,bookid,reviewer_name,content,rating,published_date)
values
(1,1,'John Smith','My First Review',4,'2017-12-10 05:50:11'),
(2,2,'John Smith','My Second Review',5,'2017-10-13 15:05:12'),
(3,2,'Alice Walker','Another Review',1,'2017-10-22 23:47:10')

select * from reviews

create table customers
(
id numeric(4) primary key,
name varchar(20),
age numeric(2),
address varchar(20),
salary numeric(10)
)

insert into customers(id,name,age,address,salary)
values
(1,'Ramesh',32,'Ahmedabad',200.00),
(2,'Khilan',25,'Delhi',1500.00),
(3,'Kaushik',23,'Kota',2000.00),
(4,'Chaitali',25,'Mumbai',6500.00),
(5,'Hardik',27,'Bhopal',8500.00),
(6,'Komal',22,'MP',4500.00),
(7,'Muffy',24,'Indore',10000.00)

select * from customers

create table employee
(
id numeric(4) primary key,
name varchar(20),
age numeric(2),
address varchar(20),
salary numeric(10)
)

insert into employee(id,name,age,address,salary)
values
(1,'Ramesh',32,'Ahmedabad',200.00),
(2,'Khilan',25,'Delhi',1500.00),
(3,'Kaushik',23,'Kota',2000.00),
(4,'Chaitali',25,'Mumbai',6500.00),
(5,'Hardik',27,'Bhopal',8500.00),
(6,'Komal',22,'MP',null),
(7,'Muffy',24,'Indore',null)

select * from employee

create table orders
(
oid numeric(4) primary key,
date datetime,
id numeric(4) references customers(id),
amount numeric(5)
)

insert into orders(oid,date,id,amount)
values
(102,'2009-10-08 00:00:00',3,3000),
(103,'2009-10-08 00:00:00',3,1500),
(104,'2009-11-20 00:00:00',2,1560),
(105,'2008-05-20 00:00:00',4,2060)


--Execution of Queries:-

select * from books where author like '%er';

select title,author,reviewer_name from books join reviews on books.id=reviews.id;

select reviewer_name from reviews group by reviewer_name having count(*)>1;

select name from customers where address like '%o%'

select count(id) from employee

select LOWER(name) from employee where salary is null order by lower(name);




0000000000000000000000000000000000000000000000000000000000000000000000000000000000
create table books
(
id numeric(4) primary key,
title varchar(30),
author varchar(30),
isbn numeric(20) unique,
published_date datetime
)

insert into books(id,title,author,isbn,published_date) values(1,'My First SQL book','Mary Parker',981483029127,'2012-02-22 12:08:17'),
(2,'My Second SQL book','John Mayer',857300923713,'1972-07-03 09:22:45'),
(3,'My Third SQL book','Cary Flint',523120967812,'2015-10-18 14:05:44')

select * from books

create table reviews
(
id numeric(4) references books(id),
bookid numeric(4),
reviewer_name varchar(30),
content varchar(30),
rating numeric(4),
published_date datetime
)

insert into reviews(id,bookid,reviewer_name,content,rating,published_date)
values
(1,1,'John Smith','My First Review',4,'2017-12-10 05:50:11'),
(2,2,'John Smith','My Second Review',5,'2017-10-13 15:05:12'),
(3,2,'Alice Walker','Another Review',1,'2017-10-22 23:47:10')

select * from reviews

create table customers
(
id numeric(4) primary key,
name varchar(20),
age numeric(2),
address varchar(20),
salary numeric(10)
)

insert into customers(id,name,age,address,salary)
values
(1,'Ramesh',32,'Ahmedabad',200.00),
(2,'Khilan',25,'Delhi',1500.00),
(3,'Kaushik',23,'Kota',2000.00),
(4,'Chaitali',25,'Mumbai',6500.00),
(5,'Hardik',27,'Bhopal',8500.00),
(6,'Komal',22,'MP',4500.00),
(7,'Muffy',24,'Indore',10000.00)

select * from customers

create table employee
(
id numeric(4) primary key,
name varchar(20),
age numeric(2),
address varchar(20),
salary numeric(10)
)

insert into employee(id,name,age,address,salary)
values
(1,'Ramesh',32,'Ahmedabad',200.00),
(2,'Khilan',25,'Delhi',1500.00),
(3,'Kaushik',23,'Kota',2000.00),
(4,'Chaitali',25,'Mumbai',6500.00),
(5,'Hardik',27,'Bhopal',8500.00),
(6,'Komal',22,'MP',null),
(7,'Muffy',24,'Indore',null)

select * from employee

create table orders
(
oid numeric(4) primary key,
date datetime,
id numeric(4) references customers(id),
amount numeric(5)
)

insert into orders(oid,date,id,amount)
values
(102,'2009-10-08 00:00:00',3,3000),
(103,'2009-10-08 00:00:00',3,1500),
(104,'2009-11-20 00:00:00',2,1560),
(105,'2008-05-20 00:00:00',4,2060)


--Execution of Queries:-

select * from books where author like '%er';

select title,author,reviewer_name from books join reviews on books.id=reviews.id;

select reviewer_name from reviews group by reviewer_name having count(*)>1;

select name from customers where address like '%o%' and customers.address=customers.address

select customers.date,customers.count(id) from employee 

select LOWER(name) from employee where salary is null order by lower(name);


