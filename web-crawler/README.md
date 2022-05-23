## WEB CRAWLER ##

1. BFS with FIFO queue should be used to crawl the webpages.

**Design Deep Dive**

Url seeder needs to come up with a logic from where it can start the crawling process and feeds that
to URL frontier.

URL frontier saves the list of URLs to be downloaded. It can maintain FIFO queue. 
To enforce politeness we can implement different queues saving URLs from different HOSTNAMES.
Each queue can save URLs from same hostname and can add delays between workers processing URLs 
from same queue.

HTML Downloader needs to go to DNS resolver to download to resolve hostnames to IP addresses to
download the HTML page. To reduce calls to DNS resolver a local cache can be maintained which can
be regularly updates the hostname and IP address mappings.

Content Parser will parse the HTML content to check for malformed web pages.

Content seen? will see if the content is already seen. If already seen discard the web page otherwise
save it in content storage. 
Instead of comparing entire text of the webpages we can compare the hashes of the web pages.

Link extractor will extract the links from the web pages.

URL filter will check for any other links which are not URLs.

URL seen will check if the URL has already been seen or not. if not feed it to URL frontier and save it 
in URL storage.


