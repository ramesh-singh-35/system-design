**DESIGN CONSISTENT HASHING**

1. In modular approach of hashing most of the keys will also fall into new server destinations which will
result in cache misses.
   
2. In consistent hashing only **k/n** keys needs to be remapped where k is the no of keys and n is total 
no of slots.
   
3. Hash Ring: With same hash function we can map servers on hash ring on the basis of IP or name.

4. Keys will be mapped to the first server encountered on hash ring while moving clockwise.

5. To fix non-uniform distribution of keys we can put virtual/replica nodes in our hash ring.
