## Unique ID Generator

1. Multi Master replication
2. UUID
3. Ticket Server
4. Twitter snowflake approach

**Twitter Snowflake Approach**

Total bits reserved for unique bid is 64 bits.

1. 1 bit is reserved for signed bit. Initially it can be 0 and can be used in future for distinguishing positive and negative 
numbers.
   
2. Next 41 bits is reserved for timestamp, and it will be represented in epoch. Generator can
convert UTC time to epoch.

3. Next 5 bits will be for datacenter id which will be configured at the application startup. 
It can support 32 data centers.

4. Next 5 bits will be for machine id which again can be configured at the application startup.
It can support 32 machines within each data centres.
   
5. Last 12 bits are reserved for sequence id which will increment by 1 and resets to 0 every millisecond.
So we can generate 4096 IDs per milliseconds.
