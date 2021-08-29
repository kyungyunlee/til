# ACID properties

2021.08.29

ACID in relational database system! 

## First, what is a transaction?

It is just a series of queries (SELECT, UPDATE, UPDATE ...), which is just grouped as one unit of work. 

You begin, commit and rollback transactions. 

## ACID 

### Atomicity 

A single transaction is atomic, meaning that all queries of a transaction are succesful or all are unsuccessful. There is nothing in the middle. 

### Consistency 

* Consistency in data : comes from atomicity and isolation 

* Consistency in read 

  When the transaction is committed, can someone read the committed change immediately? NO. 

  Eventual consistency! (In case of multi-server database, which is practically every database server these days.)

  WIthout consistency in data, consistency in read cannot happen, of course.

### Isolation

Can my current transactions see other transactions ? 

**Read phenomena** - Caused by lack of isolation 

* Dirty reads: Reading uncommitted data 

* Non-repeatable reads : Reading committed "UPDATE" operations

  A row is updated by another transaction, and you may be reading it in the middle of your transaction. 

* Phantom reads : Reading committed "INSERT" or "DELETE" operations 

  A row is inserted, and now you are reading another extra row in the middle of your transaction.

**Isolation levels** - You can set this at the beginning of your transaction. Ex. "set isolation level"

1. Read uncommitted
2. Read committed : Each query reads committed changes that happened before its query. 
3. Repeatable reads : Each query reads committed changes that happened before the current transaction. 
4. Serializable : No concurrency. 

![1_NppBgUymDiDLwBJjAvqbEQ](https://i.loli.net/2021/08/29/roLmcJb1XiZfIlG.png)

### Durability 

Committed transactions must be saved in a persistent, non-volatile storage 

