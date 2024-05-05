# What is Consistent Hashing?
Consistent hashing is a technique used in distributed computing to efficiently distribute and balance data across  
multiple servers or nodes in a consistent manner, even as the number of nodes changes. It ensures that when nodes are  
added or removed, only a fraction of the keys need to be remapped, minimizing the impact on the system. This is achieved  
by mapping each data item to a point on a ring, and each node is assigned to a range of points on the ring. When a data  
item is hashed, it is assigned to the nearest server in an anti/clockwise direction on the ring.