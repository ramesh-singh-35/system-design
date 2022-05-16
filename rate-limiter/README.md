**Design Rate Limiter**

1. Throttled users need to send 429 response back to let them know their requests have been blocked.
2. Different algorithms that can be used for rate limiting:

a. Token bucket algorithm.
In this algorithm we have a fixed bucket size and a predefined rate filler which fills the bucket with specified tokens.
If all the tokens are being taken from the bucket, new requests will be rejected.

b. Leaking bucket algorithm
It is similar to token-bucket algorithm. Here we have a queue of a fixed size and tasks are processed within a specific time period.
If queue size is full, requests will be rejected.

c. Fixed window counter algorithm
In this algorithm the timeline is divided into different windows with fixed length.
Each request increments the counter for that window.
If counter reaches the threshold, requests will be rejected.

