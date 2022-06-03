## SEARCH AUTOCOMPLETE SYSTEM ##

There are 2 important components in this system: Data gathering service and Query Service.

A simple but not efficient implementation can be all query and frequency data can be saved in a database
table.

Then the Query service can return the top K searched queries from database using below query.

_SELECT * FROM FREQUENCY_TABLE WHERE QUERY LIKE 'prfix%'
ORDER BY FREQUENCY DESC LIMIT K_

But hitting database every time user types is not very efficient.

For data gathering we can use Trie data-structure.
Every node can be a prefix and top K queries for a node can be saved at each node.
Same value can be saved in the cache (we can have distributed cache for each letter also.) as key
and value pairs.
Cache can be updated weekly (timelines can be decided on requirements.) via taking a snapshot of the
database weekly.
For Trie DB we can have key-value Databases.




