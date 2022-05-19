##Designing Key Value Store##

**CAP Theorem**
CAP theorem states that any distributed system can only provide 2 of these features from Consistency,
Availability and Network Tolerance.

1. Data partition: 
To uniformly distribute the data amoung servers we can use consistent hashing.
   
2. Data replication
We can configure a number N and once a key is mapped to hash ring we can populate that key to first N 
servers moving clockwise.
   
With virtual nodes, the first N nodes on the ring may be owned by fewer than N physical
servers. To avoid this issue, we only choose unique servers while performing the clockwise
walk logic.

3. Consistency
Quorum consensus can guarantee consistency for both read and write operations.
Read Quorums: R(no of servers coordinators wait for a read confirmation before a read is considered successful.)
Write Quorums: W(no of servers coordinators wait for a write confirmation before a write is considered successful.)

W+R> N: Highly Consistent system
W+R< N: Low Consistent system
If W=1 and R=N, write are fast.
If R=1 and W=N, reads are fast.

4. Consistency Models
a) Strong consistency
b) Weak consistency
c) Eventual consistency
   
5. Inconsistency Resolution: versioning
   
Versioning means treating each data modification as a new immutable version of data.
Vector clock.

6. Handling failures
Gossip protocol is used to detech failure detection.
   
``
