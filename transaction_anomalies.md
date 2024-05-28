# Dirty Read Problem
The dirty read problem in DBMS occurs when a transaction reads the data that has been updated by another transaction that is still uncommitted.  
It arises due to multiple uncommitted transactions executing simultaneously.

# Unrepeatable Read Problem
The unrepeatable read problem occurs when two or more different values of the same data are read during the read operations in the same transaction.

# Phantom Read Problem
In the phantom read problem, data is read through two different read operations in the same transaction. In the first read operation, a value of the  
data is obtained but in the second operation, an error is obtained saying the data does not exist.Phantom Reads is an extension of Non-Repeatable Reads.

# Dirty Writes
If there are two Transactions concurrently writing to the database to the same set of rows and if the first Transaction executes write  
operations followed by the second Transaction overwriting the values written by the first Transaction before it is committed, then the scenario is considered as Dirty Write.

# Lost Update
A lost update problem occurs due to the update of the same record by two different transactions at the same time.
In simple words, when two transactions are updating the same record at the same time in a DBMS then a lost update problem occurs. The first transaction  
updates a record and the second transaction updates the same record again, which nullifies the update of the first transaction. As the update by the  
first transaction is lost this concurrency problem is known as the lost update problem.
