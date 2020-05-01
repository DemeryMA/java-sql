# java-sql

A student that completes this project shows that they can:
* Query data from a single table
* Query data from multiple tables
* Create a new datadaase using PostgreSQL

# Introduction

Working with SQL

# Instructions

ReImport the Northwind database into PostgreSQL using pgAdmin. This is the same data we used during the guided project.

clone https://github.com/pthom/northwind_psql.git

## pgAdmin

* Right Click Databases
  * Create
    * type in northwind2

* Tools -> Query Tool
  * Open file northwind.sql (from cloned repo)
  * Execute

* Look under
  * northwind2 -> Schemas -> public -> tables

* Clear query windows

Answer the following data queries. Keep track of the SQL you write by pasting it into this document under its appropriate header below. You will be submitting that through the regular fork, change, pull process.


### find all customers that live in London. Returns 6 records.
> This can be done with SELECT and WHERE clauses

"AROUT"	"Around the Horn"	"Thomas Hardy"	"Sales Representative"	"120 Hanover Sq."	"London"
"BSBEV"	"B's Beverages"	"Victoria Ashworth"	"Sales Representative"	"Fauntleroy Circus"	"London"
"CONSH"	"Consolidated Holdings"	"Elizabeth Brown"	"Sales Representative"	"Berkeley Gardens 12  Brewery"	"London"
"EASTC"	"Eastern Connection"	"Ann Devon"	"Sales Agent"	"35 King George"	"London"
"NORTS"	"North/South"	"Simon Crowther"	"Sales Associate"	"South House 300 Queensbridge"	"London"
"SEVES"	"Seven Seas Imports"	"Hari Kumar"	"Sales Manager"	"90 Wadhurst Rd."	"London"

### find all customers with postal code 1010. Returns 3 customers.
> This can be done with SELECT and WHERE clauses

"CACTU"	"Cactus Comidas para llevar"	"Patricio Simpson"	"Sales Agent"	"Cerrito 333"	"Buenos Aires"
"OCEAN"	"Océano Atlántico Ltda."	"Yvonne Moncada"	"Sales Agent"	"Ing. Gustavo Moncada 8585 Piso 20-A"	"Buenos Aires"
"RANCH"	"Rancho grande"	"Sergio Gutiérrez"	"Sales Representative"	"Av. del Libertador 900"	"Buenos Aires"


### find the phone number for the supplier with the id 11. Should be (010) 9984510.
> This can be done with SELECT and WHERE clauses

"(010) 9984510"


### list orders descending by the order date. The order with date 1998-05-06 should be at the top.
> This can be done with SELECT, WHERE, and ORDER BY clauses

11074	"SIMOB"	7	"1998-05-06"	"1998-06-03"		2	"18.44"	"Simons bistro"
11077	"RATTC"	1	"1998-05-06"	"1998-06-03"		2	"8.53"	"Rattlesnake Canyon Grocery"
11076	"BONAP"	4	"1998-05-06"	"1998-06-03"		2	"38.28"	"Bon app'"
11075	"RICSU"	8	"1998-05-06"	"1998-06-03"		2	"6.19"	"Richter Supermarkt"
11071	"LILAS"	1	"1998-05-05"	"1998-06-02"		1	"0.93"	"LILA-Supermercado"
11073	"PERIC"	2	"1998-05-05"	"1998-06-02"		2	"24.95"	"Pericles Comidas clásicas"


### find all suppliers who have names longer than 20 characters. You can use `length(company_name)` to get the length of the name. Returns 11 records.
> This can be done with SELECT and WHERE clauses

2	"New Orleans Cajun Delights"	"Shelley Burke"	"Order Administrator"	"P.O. Box 78934"	"New Orleans"	"LA"
3	"Grandma Kelly's Homestead"	"Regina Murphy"	"Sales Representative"	"707 Oxford Rd."	"Ann Arbor"	"MI"
5	"Cooperativa de Quesos 'Las Cabras'"	"Antonio del Valle Saavedra"	"Export Administrator"	"Calle del Rosal 4"	"Oviedo"	"Asturias"
8	"Specialty Biscuits, Ltd."	"Peter Wilson"	"Sales Representative"	"29 King's Way"	"Manchester"	
10	"Refrescos Americanas LTDA"	"Carlos Diaz"	"Marketing Manager"	"Av. das Americanas 12.890"	"Sao Paulo"	
11	"Heli Süßwaren GmbH & Co. KG"	"Petra Winkler"	"Sales Manager"	"Tiergartenstraße 5"	"Berlin"	
12	"Plutzer Lebensmittelgroßmärkte AG"	"Martin Bein"	"International Marketing Mgr."	"Bogenallee 51"	"Frankfurt"	


### find all customers that include the word 'MARKET' in the contact title. Should return 19 records.
> This can be done with SELECT and a WHERE clause using the LIKE keyword

> Don't forget the wildcard '%' symbols at the beginning and end of your substring to denote it can appear anywhere in the string in question

> Remember to convert your contact title to all upper case for case insenstive comparing so upper(contact_title)

"BLONP"	"Blondesddsl père et fils"	"Frédérique Citeaux"	"Marketing Manager"	"24, place Kléber"	"Strasbourg"
"CENTC"	"Centro comercial Moctezuma"	"Francisco Chang"	"Marketing Manager"	"Sierras de Granada 9993"	"México D.F."
"FAMIA"	"Familia Arquibaldo"	"Aria Cruz"	"Marketing Assistant"	"Rua Orós, 92"	"Sao Paulo"
"FRANK"	"Frankenversand"	"Peter Franken"	"Marketing Manager"	"Berliner Platz 43"	"München"
"FRANR"	"France restauration"	"Carine Schmitt"	"Marketing Manager"	"54, rue Royale"	"Nantes"
"GALED"	"Galería del gastrónomo"	"Eduardo Saavedra"	"Marketing Manager"	"Rambla de Cataluña, 23"	"Barcelona"
"GREAL"	"Great Lakes Food Market"	"Howard Snyder"	"Marketing Manager"	"2732 Baker Blvd."	"Eugene"


### add a customer record for   
* customer id is 'SHIRE'
* company name is 'The Shire'
* contact name is 'Bilbo Baggins'
* the address is '1 Hobbit-Hole'
* ths city is 'Bag End'
* the postal code is '111'
* the country is 'Middle Earth'
> This can be done with the INSERT INTO clause

INSERT 0 1

Query returned successfully in 331 msec.


### update _Bilbo Baggins_ record so that the postal code changes to _"11122"_.
> This can be done with UPDATE and WHERE clauses


### list orders grouped by customer showing the number of orders per customer. _Rattlesnake Canyon Grocery_ should have 18 orders.
> This can be done with SELECT, COUNT, JOIN and GROUP BY clauses. Your count should focus on a field in the Orders table, not the Customer table

> There is more information about the COUNT clause on [W3 Schools](https://www.w3schools.com/sql/sql_count_avg_sum.asp)

"7"	"Wilman Kala"
"10"	"Magazzini Alimentari Riuniti"
"3"	"The Cracker Box"
"9"	"Wellington Importadora"
"4"	"Let's Stop N Shop"
"8"	"Furia Bacalhau e Frutos do Mar"
"6"	"Toms Spezialitäten"


### list customers names and the number of orders per customer. Sort the list by number of orders in descending order. _Save-a-lot Markets should be at the top with 31 orders followed by _Ernst Handle_ with 30 orders. Last should be _Centro comercial Moctezuma_ with 1 order.
> This can be done by adding an ORDER BY clause to the previous answer

"31"	"Save-a-lot Markets"
"30"	"Ernst Handel"
"28"	"QUICK-Stop"
"19"	"Hungry Owl All-Night Grocers"
"19"	"Folk och fä HB"
"18"	"HILARION-Abastos"
"18"	"Rattlesnake Canyon Grocery"


### list orders grouped by customer's city showing number of orders per city. Returns 69 Records with _Aachen_ showing 6 orders and _Albuquerque_ showing 18 orders.
> This is very similar to the previous two queries, however, it focuses on the City rather than the CustomerName




## Data Normalization

Note: This step does not use PostgreSQL!

Take the following data and normalize it into a 3NF database.  You can use the website https://www.tablesgenerator.com/markdown_tables# to help generate Markdown Tables.

| Person Name | Pet Name | Pet Type | Pet Name 2 | Pet Type 2 | Pet Name 3 | Pet Type 3 | Fenced Yard | City Dweller |
|-------------|----------|----------|------------|------------|------------|------------|-------------|--------------|
| Jane        | Ellie    | Dog      | Tiger      | Cat        | Toby       | Turtle     | No          | Yes          |
| Bob         | Joe      | Horse    |            |            |            |            | No          | No           |
| Sam         | Ginger   | Dog      | Miss Kitty | Cat        | Bubble     | Fish       | Yes         | No           |

---
## Stretch Goals

### delete all customers that have no orders. Should delete 17 (or 18 if you haven't deleted the record added) records.
> This is done with a DELETE query

> In the WHERE clause, you can provide another list with an IN keyword this list can be the result of another SELECT query. Write a query to return a list of CustomerIDs that meet the criteria above. Pass that to the IN keyword of the WHERE clause as the list of IDs to be deleted
 
> Use a LEFT JOIN to join the Orders table onto the Customers table and check for a NULL value in the OrderID column

## Create Database and Table

### After creating the database, tables, columns, and constraint, generate the script necessary to recreate the database. This script is what you will submit for review. 

- use pgAdmin to create a database, naming it `budget`.
- add an `accounts` table with the following _schema_:

  - `id`, numeric value with no decimal places that should autoincrement.
  - `name`, string, add whatever is necessary to make searching by name faster.
  - `budget` numeric value.

- constraints
  - the `id` should be the primary key for the table.
  - account `name` should be unique.
  - account `budget` is required.
