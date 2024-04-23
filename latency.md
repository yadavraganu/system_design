Latency is the amount of time in milliseconds (ms) it takes a single message to be delivered. The concept can be applied to any  
aspect of a system where data is being requested and transferred. You're probably already familiar with the latency of  
web requests as a user of the internet - some pages are really snappy and quick to use, and others take a long time to  
load and lag as you interact with them.

In a distributed system we might be interested in the latency of a database returning the results of a query. If the database is  
a substantial source of latency that could indicate we need to add an index or choose a different database model.

As another example, we might be interested in the effects a caching layer has on latency - if a cache is placed effectively it  
can lower latencies by making it faster to retrieve data. But if it's placed ineffectively a cache can raise latencies by introducing  
extra computational steps to the response.
