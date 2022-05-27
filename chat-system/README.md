##CHAT SYSTEM##

1. HTTP protocol can be used while sender sends message to the chat server.

2. For clients receiving the messages from the chat server we can use the below 3 methods.

a) Polling : Lots of server resources will be wasted while answering questions for which response is 
no most of the time.
b) Long Polling: Again waste of resources for inactive users.
c) Web sockets

Web sockets will be used for both sending and receiving side.

Data model : User details, group details, friend lists can be saved in relational databases.
Messages can be saved in KV non-relational databases.

message_id: This will be the key
message_text:
message_from:
message_to:
created_at:

for Group chats: message_id and group_id can be composite key.

message_id:
group_id:
message_from:
message_text:
created_at:

For availability presence, whenever user logins it's status will be changed to available in presence server.
and published to it's friends queues.
When user logout his presence will be updated to offline.
Also when user's internet disconnects, clients need to sent heartbeats to chat server within a fixed
time period, if not they will consider offline and status will be changed to offline.


