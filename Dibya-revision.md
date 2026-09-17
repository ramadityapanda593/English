\-------------- Database-------------------

Part -1: Common - DB fundamental

Part -2: SQL, Normalization, Join, Transaction.

Part- 3: SQL-advance View, subquery, ctes, etc.

Part -4: Transition - Distributed DB

Part- 5: no-sql

\-------------------Part-1-------------------------

Data

text, number, symbol

audio, video, image

&#x20;raw and unorganized data, meaningless, unordered and can't be analyzed



Information: Organized, related, meaningful and can be analyzed





Where data is stored?

Organize and store in a specific format is called database;

Database: We know where to store, physical storage

where exactly data is stored.



DBMS: it is a software which manages database to perform crud operation.

easily access, manage and update data in database;



it helps us to interact with database;



Database --> DBMS --> GUI/CLI, Application --> User interact with the help of GUI/CLI, Application

We install DBMS like MySQL, sql server, pl sql, oracle etc

And those DBMS software provide GUI/CLI(cmd prompt) or application interface(MySQL Workbench) to interact with database;



DBMS installation:



DBMS vs File system

File system dis advantage and DBMS overcome them

ex

1\. Data Redundancy and inconsistency ✅

2\. Difficulty in accessing data ✅ Performing crud operation was difficult.

3\. Data isolation

4\. Integrity problems

5\. Atomicity problems

6\. Concurrent-access anomalies

7\. Security problems ✅ in DBMS we follow the Constraint (Entity integrity, Referential, Domain etc.)





Client-Server- Database

Client - Browser from where user interact with the application.

Server - the application hosted and provide response to the client request.



DBMS Architecture

1-tier

2-tier

3-tier



1-tier

The Application, User interface, and Database are on the same system.



The client directly communicates with the database.

There is no separate application/server layer.

Ex: A desktop application directly accessing a MySQL database.

Example: MS Access application where the application and database are stored on the same PC.



2-tier

The Client application communicates directly with a Database server.

Example: Bank Desktop Application

A bank employee uses a desktop banking application.

The application sends requests directly to the bank's database server.

Bank Employee → Banking Application → Database Server



3-tier - widely used

The system is divided into three layers: presentation, application/business logic, and database.

view/External/presentation

Conceptual/Logical

Physical/Internal



Example: Online Shopping Website (Amazon-like)

When you buy a phone:

Customer → Website → Application Server → Database

Presentation layer: Website/app where you search and click Buy Now

Business layer: Checks product availability, calculates price, processes the order

Database layer: Stores customer, product, payment, and order information



3-Tier Architecture 	= How applications communicate.

3-Schema Architecture 	= How database data is organized and viewed.





1-tire arch: \[User/client/Browser, Application (VScode), Database] – all in single machine

2- tier arch: \[Browser \& Application], \[ Database] – two different machines

Ex: Banking application, Railway application.



3-tier arch:   \[User/client/Browser], 		\[Application (VScode)], 	\[Database] – 3 diff. machine

3-Tier Architecture = How applications communicate with each other.

Or how app. Are interconnected with each other.





Database: focus

3-Schema Architecture = How database data is organized and viewed.

Schema  Structure

Means its show, the structure of data in different level.



View : text, number, audio, video, image, pdf, url etc

Conceptual : Table, row, column, relationship, 

&#x09;	mongodb(document based), redis(key:value)



Physical: Bit, Bytes, tree, graph, hashmap etc.







ex: Instagram

Three Schema Architecture

View 			--> application that we use

Conceptual/logical 	--> data stored in Table(SAL)/Document(NoSQL-mongodb) -- text, number, audio, video, image etc.

Physical 		--> actual data is stored, using DSA  		 -- bit, byte



Physical level / Internal level

1\. How the data are stored

2\. Low-level data structures used. (Bit, byte)

3\. Describes physical storage structure of DB



Logical level / Conceptual level:

1\. what data are stored in DB

2\. Table, Column, row and what relationship exists.

3\. Goal: ease to use.



View level / External level:

1\. Highest level of abstraction

2\. User interact with the application here.

3\. Providing different view to different end-user.





Instances and Schemas

Database Schema is the actual structure of the database.

Schema doesn’t change frequently.



Database Instance - Data present in the database at a particular time/moment.

Data may change frequently.



Data independence:

It is feature, changing in one level without affecting the higher level.

1\. Physical DI

2\. Logical DI





Data Models:

A data model is a collection of concepts used to describe

how data is organized, stored, related, and accessed in a database.



Types of Data Models

There are mainly three types:

1\. Hierarchical Data Model

&#x09;Data is organized in a tree-like structure (parent → child).

&#x09;Each child usually has only one parent. and parent can't travel to Child.

&#x09;Example:

&#x09;College → Department → Students



2\. Network Data Model

&#x09;Data is organized as a graph/network.

&#x09;A record can have multiple parent and child records.

&#x09;Example:

&#x09;A student can enroll in multiple courses, and each course can have multiple students.

3\. Relational Data Model

&#x09;Data is stored in tables (rows and columns).

&#x09;Tables are connected using keys.



4\. Object Orientated

5\. Object-Relational model

5\. ER model





Collection of Date --> ER Model --> now decide where you want to implement

1\. Hierarchical Model

2\. Network Model

3\. Relational model.





Note: Before implementing, any how you have to make an ER diagram.

&#x20;



an entity --> one table(student) --> column/attribute --> row

an entity --> one class(student) --> variable --> object/instance/row



ER diagram

Student - student id

&#x09;- name

&#x09;- age

&#x09;- class

&#x09;- dept





student

|studentid|name|age|class|dept|
|-|-|-|-|-|
||||||
||||||



Object oriented



class Student {
int studentID

&#x09;string name

&#x09;int age

&#x09;int class

&#x09;char dept

}



Student  stu1 = new Student()

&#x09;stu1.studentId=1





ER diagram

Entity - A real world object, which has physical or logics existence.

Physical - human, animal, etc.

Logical - University, Medical etc.

ex: student, teacher, course etc.



Attribute

1. Key attribute (id)
2. simple attribute/single valued attribute (name)
3. Multi valued attribute (phone no, hobbie, skills)
4. Derived attribute (age)
5. Composite attribute (address)





Relationship:

it can be determined by the help of no.of Entity.

1. Unary relationship (Means only one entity participate in the relationship)

ex: Person: Person(male) marries to Person(Female)



2\. Binary Relationship (Means exactly two entity participate in the relationship)

ex:

Student --> Teacher

Student --> Course



Cardinality: means how two entity are connected with each other

means how their instances are related to each other

1:1

1:M

M:1

M:N



3\. Ternary Relationship(Means exactly three entity participate in the relationship)

ex: Passenger --> Airplane --> seat booking



4\. N-ary Relationship (Means exactly 'n' entity participate in the relationship)



Note: Mostly Unary and Binary relationship is used and we have to learn them and use them.



Summary

ER diagram

1. Entity
2. Attribute
3. Relationship
4. Cardinalates



Degree and Cardinality

Degree: No.of Entity participate in a relationship.

Cardinality: How to entity are related with each other.





How to convert ER diagram to Table



Strong Entity → Table -> make a separate table.

Weak Entity → Table + Owner (Strong entity) PK



Key Attribute(PK)  Column

Simple Attribute → Column

Composite Attribute(Address) → Break into Columns

Multi-valued Attribute(Phone no) → Separate Table

Derived Attribute(age) → Usually Ignore



1:1 Relationship → FK in one table

1: N Relationship → FK on N side

M: N Relationship → New Junction Table, and it should contain, PK of both the table.



Unary Relationship → Self-Referencing FK

Binary relationship -> PK and FK relation

Ternary Relationship → New Tables

Specialization → Multiple Mapping Options





Table terminologies

Table

Row, Tuple, Record

Column, Field, Attribute etc

Degree: No.of Column present in a Relation/Table.

Cardinalities: no.of Record/Tuple/Row present in a table.





Key:

Super key: all possible combination of key, that can uniquely identify each row of relation/table.

A set of one or more attributes (columns) that can uniquely identify every tuple (row) in a table.



Candidate key: minimal super key;

Primary key: one candidate key selected as PK

Alternate key: the keys which are not selected as PK;

or After PK selection other candidate keys are called AK



Foreign key: It is a PK of one table, reference to another table as FK;

Natural key: A unique identifier/attribute that already exists in the real world and possesses business meaning;

surrogate key: An artificially created identifier generated by the database system that possesses no intrinsic business meaning.





Constraints:

These are set of rules and regulation which are applied to DB and table, to make them consistence.

1. Entity Integrity Constraint. Primary key
2. Referential IC: FK
3. Domain IC: applied to the columns of the table.

Default, Check, Not Null, Unique etc.

\----------------------------------------------------------------------------------------------------------

SQL- Structured Query Language

\-------------------------------

SQL- it is Standard/Language, which is used to interact with the Relational Database;

where we can access, modify, delete, means can perform CRUD operations;



DBMS: Database Management System: it is a software, which is used to interact with DB.

DBMS can be either Relational(SQL) or Non-Relational(No-SQL);



Relational DB is implemented by some DBMS companies by following the standard of SQL;

types:

1. MySQL
2. PostgraseSQL
3. Oracle
4. SQL server
5. etc.



Where they store data in the form of Database --> Table --> Column/Row;

To interact with Relational DB, SQL provides some language

1. DDL(Data Definition Language) --> Database, Table, Column  			--> Create, Alter, Drop, Trunk(ACDT), Rename
2. DML(Data manipulation language) --> Directly interact with Data;		--> Insert, Update, Delete
3. DQL(Data Query language) --> Select the data using where and clause		--> Select, where, form, clause, order by, Group by, having
4. DCL(Data control Language) --> Give access					--> Grant, Revoke
5. TCL(Transaction Control Language) --> main aim to keep the DB consistency.	--> Save point, Rollback, Commit;



Data Types:

1. Numeric		Int, Float, Double, Decimal
2. Character		Char, varchar, text
3. Date and Time	DATE, TIME, DATETIME, YEAR
4. Boolean		BOOL(true, false) (yes, no) etc.
5. Binary		BLOB(Binary LOB)(image, audio, video), CLOB(Character LOB)(Massive character data)
6. JSON





Data type conversion:

1. Implicit 	automatically converts
2. Explicit	Need to Convert manually

Two common methods:

1. CAST()	--> all DB supports.

2\. CONVERT() 	--> only SQL server.





Operators:

1. Arithmatic
2. Assignment
3. Bitwise
4. Logical
5. Compound/shorthand +=
6. Special Operator

IN, NOT IN, LIKE, NOT LIKE, BETWEEN,

\---------------------------------------------------

Join- always learn after Normalization

\---------------------------------------------------

Normalization:

It is a process to divide a big table into no.of smaller and related table.

1. To reduce data Redundancy.
2. To increase data integrity and consistency.
3. To avoid anomalies.
4. Optimized Disk Storage.
5. Simplified Database Maintenance.



How to achieve normalization?



Functional Dependency

f: X --> Y;    just assume X is a PK;

X: Determinant (can be single attribute or combination of multiple attribute)

Y: Dependent (Y always single)



1. Fully FD		Y totally dependent on X, means Y should be determined by all the attribute of X;
2. Partial FD		Y can be determined by any of the attribute of X;



f: X--> Y

1. Trivial FD, 			Y subset of X
2. Non-trivial FD,		at least one element of Y is present in X;
3. Completely Non-Trivial FD, 	Y is totally different then X, means no common attribute;



Candidate key: 		Minimal super key;

Prime attribute: 	Attribute present in Candidate key;

Non-Prime attribute:	Attribute not present in Candidate key;



How to find Candidate key?

Ans: Attribute Closure is used to find the Candidate key;



\*\*\*\*Note: Do lot of examples;



Armstrong axioms: f: X --> Y

1. Reflexive: 				(If Y ⊆ X, then X → Y)
2. Augmentation: 			(If X → Y, then XZ → YZ)
3. Transitivity Rule 			(If X → Y and Y → Z, then X → Z)



The Three Secondary Axioms (Derived Rules)

1. Decomposition / Splitting Rule 	(If X → YZ, then X → Y and X → Z)
2. Composition Rule 			(If X → Y and W → Z, then XW → YZ)
3. Pseudo-Transitivity Rule 		(If X → Y and WY → Z, then WX → Z)



Anomalies

1. Insertion
2. Update
3. Deletion



Normal forms

UNF

1NF	Atomic

2NF	No Partial FD

3NF	No Transitive FD

BCNF	X(Determinant) should be a super key

4NF	Multi Valued Dependency (Hobbies, Skill, Language)

5NF	Join Dependency



Decomposition

1. Lossy Decomposition
2. Lossless Decomposition



Denormalizations. here we combine the table actually, not like join;



Join:

Inner-Join

Left-Join

Right-Join

Full-Join

Self-Join

Cross(Cartesian Product)

\-----------------------------------------------------------------------

Transaction

ACID property

1. Atomicity		---> all or nothing
2. Consistency		---> DB should be stable, before and after transaction.
3. Isolation		---> no.of transition should be performed isolate way.
4. Durability		---> once data committed, data should be save in DB, if crash, disaster happens.



States

Active, partial committed, Committed, Terminated.

&#x09;	 Failed, Aborted, Terminated.



Transaction

\--------------------

BEGIN TRANSCATION



&#x09;SQL STATEMENTS

&#x09;SQL STATEMENTS



SAVE POINTS save\_point\_name\_1



&#x09;SQL STATEMENTS

&#x09;SQL STATEMENTS



SAVE POINTS save\_point\_name\_2



&#x09;SQL STATEMENTS

&#x09;SQL STATEMENTS



SAVE POINTS save\_point\_name\_3



Rollback / Rollback save\_point\_name

or

COMMIT;

\----------------------------

Main Goal of Transaction:: to make the DB Consistence.

ex: if multiple user use/operate the same db at a time,
Transaction helps to make them/perform them Consistently.

\----------------------------------------------------



CAP:

Consistency		--> Banking app. ERP app etc  	--> to get perfect data;

Availability		--> Social media etc.	      	--> it doesn't provide the perfect data, but it is available all the time. it takes time to sync.

Partition Tolerance	--> For Distributed database the main problem is network availability.

\----------------------------------------------------------------------------------------

\---------------------------------------------------------------------------

SQL functions are built-in operations that accept inputs, process data, and return a specific output value.

Function



1. Aggregate function. 			min, max, avg, sum, count
2. Scalar (Single-Row) Functions
3. Data and Time function.
4. windows function
5. Numeric / Mathematical Functions
6. String function

\------------------------------------------------------------------





Cardinality

Table: No.of row present in a table at a particular moment;



Relation: The type of relationship exists between two entities;

ex: 1:1, 1:m, m:1, m:n

































html, css, js, reactjs - frontend

nodejs, expressjs,  - backend

mongodb, sql 	- database

restapi, etc. - api



5 project;

AWS- CloudFloks

