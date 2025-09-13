/* ------*****------ Create Database of Supply Chain ------*****------ */

create database SupplyChain;
use SupplyChain;

/* ---- Creating Tables & Indexes ------ */


create table Customer (
Id int auto_increment,
Name varchar(40) not null,
City varchar(40) null,
Phone varchar(40) null,
constraint pkCustomer primary key(Id)
);

create index idxCustomerName on Customer (
Name ASC
);

create table Orders (
Id int auto_increment,
OrderDate varchar(40) not null,
OrderNo varchar(40) null,
CustomerId int not null,
TotalAmount decimal(12,2) null default 0,
constraint pkOrders primary key(Id)
);

create index idxOrdersOrderDate on Orders (
OrderDate ASC
);

create table OrderItem (
Id int auto_increment,
OrderId int not null,
ProductId int not null,
UnitPrice decimal(12,2) not null default 0,
Quantity int not null default 1,
constraint pkOrderItem primary key(Id)
);

create index idxOrderItemOrderId on OrderItem (
OrderId ASC
);

create table Product (
Id int auto_increment,
ProductName varchar(50) not null,
SupplierId int not null,
UnitPrice decimal(12,2) null default 0,
Package varchar(30)  null,
IsDiscontinued bit not null default 0,
constraint pkProduct primary key (Id)
);

create index idxProductProductName on Product (
ProductName ASC
);

create table Supplier (
Id int auto_increment,
CompanyName varchar(40) not null,
ContactName varchar(40) not null,
City varchar(20) null,
Phone varchar(20) null,
constraint pkSupplier primary key(Id)
);

create index idxSupplierCompanyName on Supplier (
CompanyName ASC
);



/* ----- Adding Forign Key Constraints ----- */

alter table Orders add foreign key(CustomerId) references Customer(Id);
alter table OrderItem add foreign key(ProductId) references Product(Id);
alter table OrderItem add foreign key(OrderId) references Orders(Id);
alter table Product add foreign key(SupplierId) references Supplier(Id);


/* Adding On delete cascade for if row deleted in parent table then it will auto delete the child row/record
But we need these records for future even parent record is deleted so we don't actually apply that
alter table Orders add constraint pkOrders primary key(Id) on delete cascade;
*/



/* ------ Inserting Data into Tables ------- */

Insert into Customer(Name, City, Phone) values 
('Ali Raza', 'Lahore', '0321-5245987'),
('Sara Naeem', 'Karachi', '0301-6595123'),
('Abdullah Bari', 'Quetta', '0312-8526347'),
('Sana Javed', 'Islamabad', '0346-7461523'),
('Bilal Mehar', 'Multan', '0312-5621478'),
('Bushrah Shah', 'Lahore', '0314-2536369'),
('Amar Yasir', 'Lahore', '0322-8975984'),
('Tayyab Sabir', 'Peshawar', '0324-3214562'),
('Usman Khan', 'Peshawar', '0326-5278916'),
('Khalida Bibi', 'Islamabad', '0344-5233300'),
('Shazad Ihsan', 'Karachi', '0300-4182931'),
('Javaria Aslam', 'Multan', '042-9856322'),
('Rabiya Islam', 'Karachi', '0326-5666301'),
('Nigarsh Batool', 'Islamabad', '0312-0012030'),
('Lamya Shah', 'Lahore', '0307-5239610'),
('Haider Ali', 'Quetta', '0319-1213111'),
('Hassan Nazeer', 'Multan', '0314-5858589'),
('Amir Akhtar', 'Islamabad', '0323-2312001'),
('Nasir Ali', 'Lahore', '0320-1090950'),
('Shair Afgan', 'Karachi', '0345-6137942');

insert into Orders (Id, OrderDate, CustomerId, TotalAmount, OrderNo) values
(1,'Jul  4 2025 12:00:00',5,440.00,'542378'),
(2,'Jul  5 2025 12:00:00',19,1863.40,'542379'),
(3,'Jul  8 2025 12:00:00',14,1813.00,'542380'),
(4,'Jul  8 2025 12:00:00',14,670.80,'542381'),
(5,'Jul  9 2025 12:00:00',16,3730.00,'542382'),
(6,'Jul 10 2025 12:00:00',4,1444.80,'542383'),
(7,'Jul 11 2025 12:00:00',1,625.20,'542384'),
(8,'Jul 12 2025 12:00:00',6,2490.50,'542385'),
(9,'Jul 15 2025 12:00:00',8,517.80,'542386'),
(10,'Jul 16 2025 12:00:00',5,1119.90,'542387'),
(11,'Jul 17 2025 12:00:00',20,2018.60,'542388'),
(12,'Jul 18 2025 12:00:00',13,100.80,'542389'),
(13,'Jul 19 2025 12:00:00',16,1746.20,'542390'),
(14,'Jul 19 2025 12:00:00',11,448.00,'542391'),
(15,'Jul 22 2025 12:00:00',15,624.80,'542392'),
(16,'Jul 23 2025 12:00:00',20,2464.80,'542393'),
(17,'Jul 24 2025 12:00:00',2,724.50,'542394'),
(18,'Jul 25 2025 12:00:00',7,1176.00,'542395'),
(19,'Jul 26 2025 12:00:00',8,364.80,'542396'),
(20,'Jul 29 2025 12:00:00',5,4031.00,'542397'),
(21,'Jul 30 2025 12:00:00',3,1101.20,'542398'),
(22,'Jul 31 2025 12:00:00',9,676.00,'542399'),
(23,'Aug  1 2025 12:00:00',17,1376.00,'542400'),
(24,'Aug  1 2025 12:00:00',5,48.00,'542401'),
(25,'Aug  2 2025 12:00:00',15,1456.00,'542402'),
(26,'Aug  5 2025 12:00:00',13,2142.40,'542403'),
(27,'Aug  6 2025 12:00:00',5,538.60,'542404'),
(28,'Aug  7 2025 12:00:00',12,307.20,'542405'),
(29,'Aug  8 2025 12:00:00',10,420.00,'542406'),
(30,'Aug  9 2025 12:00:00',12,1200.80,'542407'),
(31,'Aug 12 2025 12:00:00',5,1488.80,'542408'),
(32,'Aug 13 2025 12:00:00',6,468.00,'542409'),
(33,'Aug 14 2025 12:00:00',18,613.20,'542410'),
(34,'Aug 14 2025 12:00:00',19,86.50,'542411'),
(35,'Aug 15 2025 12:00:00',19,155.40,'542412'),
(36,'Aug 16 2025 12:00:00',16,1414.80,'542413'),
(37,'Aug 19 2025 12:00:00',14,1452.00,'542414'),
(38,'Aug 20 2025 12:00:00',13,2179.20,'542415'),
(39,'Aug 21 2025 12:00:00',3,3016.00,'542416'),
(40,'Aug 22 2025 12:00:00',17,924.00,'542417'),
(41,'Aug 23 2025 12:00:00',6,89.00,'542418'),
(42,'Aug 26 2025 12:00:00',11,479.40,'542419'),
(43,'Aug 27 2025 12:00:00',1,2169.00,'542420'),
(44,'Aug 27 2025 12:00:00',2,552.80,'542421'),
(45,'Aug 28 2025 12:00:00',18,1296.00,'542422'),
(46,'Aug 29 2025 12:00:00',8,848.70,'542423'),
(47,'Aug 30 2025 12:00:00',6,1887.60,'542424'),
(48,'Sep  2 2025 12:00:00',13,121.60,'542425'),
(49,'Sep  3 2025 12:00:00',4,1050.60,'542426'),
(50,'Sep  4 2025 12:00:00',7,1420.00,'542427');

insert into Supplier (CompanyName, ContactName, City, Phone) values 
('Glowing Angels', 'Ayesha Khalid', 'Lahore', '0321-4142040'),
('Iron Fitness', 'Nouman Ansari', 'Multan', '0300-2100089'),
('Blue Plastics', 'Wasif Bhatti', 'Islamabad', '0346-8594178'),
('Afzal Electronics', 'Kashif Bashir', 'Karachi', '0333-5142621'),
('Saqib Travels', 'Saqib Ihsan', 'Lahore', '0320-1030520');

insert into Product (ProductName, SupplierId, UnitPrice, Package, IsDiscontinued) values 
('Hair Oil', 1, 550.00, '50 Bottles', 0),
('Whiting Cream', 1, 260.00, '5 Cottons x 50 Creams', 0),
('Lipsticks', 1, 120.50, '100 Pieces', 0),
('FaceWash', 1, 340.00, '5 Pieces', 1),
('Soaps', 1, 80.00, '120 Pieces', 0),
('Suppliments', 2, 5500.50, '8 Packs', 0),
('Outfits', 2, 1200.00, '20 Sets', 0),
('Toys', 3, 150.00, '10 Sets', 0),
('Catllery', 3, 400.00, '5 Sets', 1),
('Bottles', 3, 800.00, '10 Bottles', 0),
('Refrigrator', 4, 120000.00, '2 Pieces', 0),
('Air Conditioner', 4, 140000.00, '6 Pieces', 0),
('Ovan', 4, 40000.00, '4 Pieces', 0),
('LED Lights', 4, 2000.00, '12 Pieces', 0),
('LEDs', 4, 15000.00, '10 Pieces', 0),
('Tents', 5, 10000.00, '5 Pieces', 0),
('Sneakers', 5, 6500.00, '2 Pairs', 1),
('Hiking Packs', 5, 40000.00, '1 Pack', 0);

insert into OrderItem (Id, OrderId, ProductId, UnitPrice, Quantity) values 
(1,1,11,14.00,12),
(2,1,2,9.80,10),
(3,1,12,34.80,5),
(4,2,14,18.60,9),
(5,2,1,42.40,40),
(6,3,1,7.70,10),
(7,3,5,42.40,35),
(8,3,5,16.80,15),
(9,4,2,16.80,6),
(10,4,7,15.60,15),
(11,4,6,16.80,20),
(12,5,10,64.80,40),
(13,5,13,2.00,25),
(14,5,16,27.20,40),
(15,6,3,10.00,20),
(16,6,9,14.40,42),
(17,6,9,16.00,40),
(18,7,14,3.60,15),
(19,7,15,19.20,21),
(20,7,14,8.00,21),
(21,8,2,15.20,20),
(22,8,16,13.90,35),
(23,8,6,15.20,25),
(24,8,5,44.00,30),
(25,9,3,26.20,15),
(26,9,17,10.40,12),
(27,10,17,35.10,25),
(28,10,3,14.40,6),
(29,10,7,10.40,15),
(30,11,8,15.20,50),
(31,11,5,17.00,65),
(32,11,12,25.60,6),
(33,12,11,8.00,10),
(34,12,18,20.80,1),
(35,13,4,7.70,16),
(36,13,7,15.60,50),
(37,13,6,39.40,15),
(38,13,10,12.00,21),
(39,14,11,8.00,20),
(40,14,15,14.40,20),
(41,15,5,17.00,12),
(42,15,7,24.00,15),
(43,15,16,30.40,2),
(44,16,6,13.90,60),
(45,16,4,3.60,28),
(46,16,3,20.70,60),
(47,16,14,8.00,36),
(48,17,1,15.20,35),
(49,17,1,7.70,25),
(50,18,17,31.20,30);


/* ------- ******* -------- Data Analysis ------- ******* -------- */
# Section A: Level 1 Questions
# 1.	Read the data from all the tables

select * from Customer;
select * from Supplier;
select * from Product;
select * from Orders;
select * from Orderitem;


# 2.	Find the city-wise count of customers
select City, count(City) as 'No of Customers' from Customer group by city;

# 3.	Display the products that are not discontinued. 
select * from Product where IsDiscontinued = 1;

# 4.	Display the list of companies along with the product name that they are supplying. 
select s.Id, s.CompanyName, s.ContactName, p.ProductName from Supplier s join Product p on s.Id=p.SupplierId;

#5.	Display customer information about who stays in 'Lahore'
select * from Customer where City = 'Lahore';

# ============== Additional: Level 1 questions ==============

#6.	Display the costliest item that is ordered by the customer.

#7.	Display supplier ID who owns the highest number of products.
select max(sp.Id as 'Supplier Id', sp.CompanyName as  'Company Name', count(p.SupplierId) as cnt_pd 
from Supplier sp join Product p on sp.id = p.SupplierId 
group by sp.Id order by sp.Id ASC) from ;


SELECT p.SupplierId, sp.CompanyName, COUNT(p.SupplierId) as product_count
FROM Product p 
JOIN Supplier sp on sp.Id=p.SupplierId
GROUP BY p.SupplierId
ORDER BY product_count DESC
LIMIT 1;

SELECT supplierid, COUNT(*) as product_count
FROM product
GROUP BY supplierid
HAVING COUNT(*) = (
    SELECT MAX(product_count) 
    FROM (
        SELECT COUNT(*) as product_count
        FROM product
        GROUP BY supplierid
    ) counts
);




# 8.	Display month-wise of the orders placed.
# we have date data in string formate so first we have to convert it to simple date formate then it will extract the month otherwise it will give Null
# Simple month() function gives month number but monthname() gives name of month
# That part — '%b %e %Y %H:%i:%s' — is a date/time format string used by MySQL’s STR_TO_DATE() function.

select count(Id) as 'Total Orders', month(str_to_date(OrderDate, '%b %e %Y %H:%i:%s')) as Month from Orders 
group by month(str_to_date(OrderDate, '%b %e %Y %H:%i:%s')) order by month(str_to_date(OrderDate, '%b %e %Y %H:%i:%s')) asc;


# 9.	Which city has the maximum number of suppliers?

select City, count(Id) as Suppliers from Supplier group by City order by City asc;


#10.	Which customers did not place any orders?

Insert into Customer(Name, City, Phone) values 
('Munna Bahi', 'Lahore', '0302-4201007');

select C.Name, count(O.CustomerId) as noofOrders from Customer as C left join Orders as O on C.Id=O.CustomerId
group by C.Name having noofOrders=0;

OR
select * from Customer where Id not in(select CustomerId from Orders);


# --------- ++++++++ Section B: Level 2 Questions:

#1.	Arrange the Product ID and Name based on the high demand by the customer.

select P.Id as "Product ID", P.ProductName as "Product Name", sum(OI.Quantity) as Quantity
from OrderItem as OI join Product as P on OI.ProductId = P.Id group by P.Id order by Quantity desc;


#2.	Display the total number of orders and total revenue delivered every month

select monthname(str_to_date(OrderDate, '%b %e %Y %H:%i:%s')) as MonthName, count(Id) as 'No of Orders', sum(TotalAmount) as 'Total Revenue' from Orders
group by MonthName;


#4.	Display the customer details whose order amount is maximum including his past orders also total orders places by him.

select C.*, count(O.CustomerId) as 'No of Orders', sum(O.TotalAmount) as Amount from Customer as C left join Orders as O
on C.Id =  O.CustomerId group by C.Id order by Amount desc limit 1;


#5.	Display the total amount ordered by each customer from high to low.

Select C.*, count(O.CustomerId) as NoOfOrders from Customer as C left Join Orders as O
on C.Id = O.CustomerId group by C.Id order by NoOfOrders desc;

# ----------- Additional Level 2 Questions:

#The sales and marketing department of this company wants to find out how frequently customers do business with them. 
# (Answer Q 6 for the same) 
#6.	Approach - List the current and previous order dates for each customer.


# We will not use group by clause as there is no aggrigate function performs here
select C.*, O.OrderDate from Customer as C join Orders as O
on C.Id = O.CustomerId order by C.Id asc;


#7.	 Find out the top 3 suppliers in terms of revenue generated by their products. 

select S.*, sum(Quantity * OI.UnitPrice) as TotalRevenue
from Supplier as S 
join Product as P on S.Id = P.SupplierId
join OrderItem as OI on P.Id = OI.Id
join Orders as O on O.Id = OI.OrderId
group by S.Id
order by TotalRevenue desc limit 3;


#8.	Display the latest order date (should not be the same as the first order date) of all the customers with customer details. 

select C.*, min(O.OrderDate) as DateOfOrder from Customer as C left join Orders as O on C.Id = O.CustomerId
group by C.Id order by C.Id asc;


#9.	Display the product name and supplier name for each order  

select O.*, P.ProductName as Product, S.CompanyName as SupplierName from Supplier as S
join Product as P on P.SupplierId = S.Id
join OrderItem as OI on OI.ProductId = P.Id
join Orders as O on O.Id = OI.OrderId
order by O.Id asc;


#Section C: Level 3 Questions:

#1.	Fetch the customer details who ordered more than 10 products in a single order.
# It will get the latest order No

select C.*, O.OrderDate, O.OrderNo, OI.Quantity from Customer as C 
join Orders as O on C.Id = O.CustomerId
join OrderItem as OI on O.Id = OI.OrderId
group by OI.Id having OI.Quantity > 10 order by C.Id;


#2.	Display all the product details with the ordered quantity size as 1. 

select P.*, OI.Quantity from Product as P left join OrderItem as OI on P.ID = OI.ProductId
where OI.Quantity = 1;


#3.	Display the companies that supply products whose cost is above 100.

select distinct S.*, P.ProductName, P.UnitPrice from Supplier as S
join Product as P on S.Id = P.SupplierId
where P.UnitPrice > 100 order by P.UnitPrice desc;


#4.	Display the customer list who belongs to the same city and arranged City-wise

select * from Customer order by City asc;


#Section D: Level 4 Questions:
  
#1.	The company sells the products at different discount rates. Refer actual product price in the product table and the selling price 
#in the order item table. Write a query to find out the total amount saved in each order then 
#display the orders from highest to lowest amount saved. 

select OI.OrderId, OI.ProductId, OI.UnitPrice as "Order Unit Price", P.UnitPrice as "Product Unit Price", 
max((P.UnitPrice - OI.UnitPrice) * OI.Quantity) as AmountSaved from Product as P 
join OrderItem as OI on P.Id = OI.ProductId
group by OI.Id order by AmountSaved desc;


# 2.	Mr. Kavin wants to become a supplier. Help him to pick: 
# 	a.	List a few products that he should choose based on demand (More than 100 Products selled).
# 	b.	Who will be the competitors for him for the products suggested in the above questions? 

select distinct S.CompanyName, S.ContactName, S.City, P.ProductName from OrderItem as OI
join Product as P on P.Id = OI.ProductId
join Supplier as S on S.Id = P.SupplierId
group by P.Id, P.ProductName, S.CompanyName having sum(OI.Quantity) > 100 order by S.CompanyName;


# 3.	Create a combined list to display customers' and suppliers' details considering the following criteria 
# 	a.	Both customer and supplier belong to the same country 
#	b.	Customers who do not have a supplier in their country
#	c.	A supplier who does not have customers in their country 

select * from Customer C join Supplier S on C.City = S.City
union all
select * from Customer C left join Supplier S on C.City = S.City where S.City is null
union all
select * from Customer C right join Supplier S on C.City = S.City where C.City is null;
