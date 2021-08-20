# 1. Relational model 

Reviewing databases with [CMU database course](https://15445.courses.cs.cmu.edu/fall2019/).

The development of DBMS and the concept of relational data model revolutionized the way users interact with the database. 
Before, the logical and physical layer of the database application made it necessary for users to update both physical and logical layer. 
Nowadays, users simply use SQL to make any queries, while the physical workings with the database is hidden as a black box and can be implemented in many different ways. 
Therefore, users do not have to worry about what is happening under cover. 

Following 3 concepts are the main ideas of the relational model
* structure: data have attributes which describe their relations 
* integrity: each attribute has to follow certain rules
* manipulation: data can be freely modified into new data

Relational algebra describes how to process queries on the database.
* select
* projection: aka. where
* union: aka. union all 
* intersection: appears in both relations. aka. intersect
* difference: appears in the first relation and not in the second relation. aka. except
* product : aka. cross join  
* join  
 
Relational model is independent of any query language implementation.