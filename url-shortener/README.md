##URL SHORTENER##

1. We can use 301 Redirect or 302 Redirect. 301 means URL is permanently directed to Long URL and browser
can cache the Long URL and can directly go to long URL for subsequent calls. 302 means temporary re-direction
and all calls will come to url-shortener server.
   
2. The method used to shorten the long url is hash the long url.

**API Endpoints**
POST - api/v1/shorten/url
User will send long URL and API will return short URL.

GET - api/vi/shorten/url/{short_url}
User will send short URL and API will send long URL back.

**Data Models**

Table: URL details
ID(Primary key)
Short URL
Long URL


**Hashing Methods**

1. Hashing+ Resolve Collision
Whenever user sends a long URL API will hash the long url using any of the common hashing techniques
such as SHA-1 and then can take first 7 characters. If Short URL exists in DB, we will append the 
predefined string to hash value and recalculate the short url. Process is repeated till a unique value is
found.
   
7 characters is used since 62^7 will result in sufficient amount of urls needed for data set.

2. Base 62 conversion
Generate a unique ID which can be incremented by 1 for every new request.
Convert the generated ID to it's base 62 value.
Store all 3, ID, short URL and long URL in database.
