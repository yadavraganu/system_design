The CAP theorem, also named Brewer's theorem after computer scientist Eric Brewer, states that any distributed data store can provide only two of the following three guarantees:  
- __Consistency :__ Every read receives the most recent write or an error.  
- __Availability :__ Every request receives a (non-error) response, without the guarantee that it contains the most recent write.  
- __Partition tolerance :__ The system continues to operate despite an arbitrary number of messages being dropped (or delayed) by the network between nodes i.e. two or more nodes are longer connected.  

When a network partition failure happens, it must be decided whether to do one of the following:
- Cancel the operation and thus decrease the availability but ensure consistency
- proceed with the operation and thus provide availability but risk inconsistency.  

![img.png](images/CAP.png)

Thus, if there is a network partition, one has to choose between consistency or availability.  
__Note :__  The consistency as defined in the CAP theorem is quite different from the consistency guaranteed in ACID database transactions.