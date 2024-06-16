# Read Anomalies

### Dirty Read
The dirty read problem in DBMS occurs when a transaction reads the data that has been updated by another transaction that is still uncommitted.It arises due to multiple uncommitted transactions executing simultaneously.

### Unrepeatable / Fuzzy Read
The unrepeatable read problem occurs when two or more different values of the same data are read during the read operations in the same transaction.

### Phantom Read
In the phantom read problem, data is read through two different read operations in the same transaction. In the first read operation, a value of the data is obtained but in the second operation, an error is obtained saying the data does not exist.Phantom Reads is an extension of Non-Repeatable Reads.  
A phantom read is when a transaction queries the same set of rows twice and receives different results. It is similar to a nonrepeatable read, but holds for range queries.

# Write Anomalies

### Dirty Writes
If there are two Transactions concurrently writing to the database to the same set of rows and if the first Transaction executes write operations followed by the second Transaction overwriting the values written by the first Transaction before it is committed, then the scenario is considered as Dirty Write.

### Lost Update
A lost update problem occurs due to the update of the same record by two different transactions at the same time.In simple words, when two transactions are updating the same record at the same time in a DBMS then a lost update problem occurs. The first transaction  
updates a record and the second transaction updates the same record again, which nullifies the update of the first transaction. As the update by the first transaction is lost this concurrency problem is known as the lost update problem.

### Write Skew
A write skew occurs when each individual transaction respects the required invariants, but their combination does not satisfy these invariants.
For example,transactions T1 and T2 modify values of two accounts A1 and A2 . A1 starts with 100$ and A2 starts with 150$. The account value is allowed to be negative, as long as the sum of the two accounts is nonnegative: A1 + A2 >= 0.  
T1 and T2 each attempt to withdraw 200$ from A1 and A2 , respectively. Since at the time these transactions start A1 + A2 = 250$, 250$ is available in total.  
Both transactions assume they’re preserving the invariant and are allowed to commit. After the commit, A1 has -100$ and A2 has -50$, which clearly violates the requirement to keep a sum of the accounts positive
