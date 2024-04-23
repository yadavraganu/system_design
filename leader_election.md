# LCR ALGORITHM FOR LEADER ELECTION
## Basics of LCR algorithm

- Most simplest, easy to implement algorithm.
- It works in a virtual ring pattern topology in a synchronous fashion , in which the nodes are assumed functioning in a  
   sync fashion in each round, i.e., they only move forward when they receive an incoming message for moving forward.
- Every node in the distributed network topology is assigned with UNIQUE UID.

## ALGORITHM STEP BY STEP

- Every node in the network participates to be the new leader.
- Each node sends a message to its neighbouring node in its right direction(assuming we are in a virtual ring topology), containing the unique UID.
- When a node receives a UID, it compares the incoming UID with its own, and  
    If the incoming is greater than its own, it forwards it  
    If the incoming is lesser than its own, it discards  
    If the incoming UID == its own, it declares itself as the new leader  
- Algorithm stops when the node receives its own UID from the network, this implies that after the entire iteration this node has the highest UID
  in the network; and hence can become the new leader.
- The newly elected leader then sends a HALT message to everyone in the topology, so that everyone stops sending the message and update locally
  about the newly elected leader.

## Complexity
Every node could potentially receive the message from every other node; the communication complexity, # messages shared, is thus O(n²).
