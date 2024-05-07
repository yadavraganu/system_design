# Optimistic Concurrency Control
With optimistic concurrency control, transactions do not obtain locks on data when they read or write. The "Optimistic"  
in the name comes from assuming that conflicts are unlikely to occur, so locks are not needed. If something does go  
wrong though, conflicts will still be prevented and everything will be OK.  
Unlike pessimistic concurrency control – which prevents conflicts from occurring by blocking them before they get a  
chance to start – optimistic concurrency control checks for conflicts at the end of a transaction.  
With optimistic concurrency control, multiple transactions can read or update the same database item without    
acquiring locks. How exactly does this work?  
Every time a transaction wants to update a database item, say a row, it will also read two additional columns added   
to every table by the DBMS – the timestamp and the version number. Before that transaction is committed, it checks  
if another transaction has made any change(s) to that row by confirming if the version number and timestamp are the same.  
If they have changed, that means another transaction has updated that row, so the initial transaction will have to be retried.


# Pessimistic Concurrency Control
With pessimistic concurrency control, the DBMS assumes that conflicts between transactions are likely to occur.  
It is pessimistic – that is, it assumes that if something can go wrong, it will go wrong. This pessimism prevents  
conflicts from occurring by blocking them before they get a chance to start.  
To prevent these conflicts, it locks the data that a transaction is using until the transaction is completed. This  
approach is 'pessimistic' because it assumes the worst-case scenario – that every transaction might lead to a conflict.  
The data is therefore locked in order to prevent conflicts from happening.