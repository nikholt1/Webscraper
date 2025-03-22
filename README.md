# Webscraper "books"
- Build in python using Scrapy
- Build one spider for scraping books from webpage https://books.toscrape.com/
- Spider build with crawling for multiple li> next pages.

Usage: 

Webscraping with writing to CSV
```
scrapy crawl book -o books.csv
```
Webscraping with writing to SQLite
```
scrapy crawl book -o books.db -t sqlite
```


## Visualization of running a crawl
```
User1@nummer1:~/books/books/spiders $ scrapy crawl book
/usr/local/lib/python3.9/dist-packages/scrapy/spiderloader.py:51: UserWarning: There are several spiders with the same name:

  BookSpider named 'book' (in books.spiders.book)

  BookSpider named 'book' (in books.spiders.books)

  This can cause unexpected behavior.
  warnings.warn(
2025-03-22 15:49:32 [scrapy.utils.log] INFO: Scrapy 2.12.0 started (bot: books)
2025-03-22 15:49:32 [scrapy.utils.log] INFO: Versions: lxml 4.6.3.0, libxml2 2.9.10, cssselect 1.3.0, parsel 1.10.0, w3lib 2.3.1, Twisted 24.11.0, Python 3.9.2 (default, Dec  9 2024, 13:57:34) - [GCC 10.2.1 20210110], pyOpenSSL 25.0.0 (OpenSSL 3.4.1 11 Feb 2025), cryptography 44.0.2, Platform Linux-6.1.21-v8+-aarch64-with-glibc2.31
2025-03-22 15:49:32 [scrapy.addons] INFO: Enabled addons:
[]
2025-03-22 15:49:32 [asyncio] DEBUG: Using selector: EpollSelector
2025-03-22 15:49:32 [scrapy.utils.log] DEBUG: Using reactor: twisted.internet.asyncioreactor.AsyncioSelectorReactor
2025-03-22 15:49:32 [scrapy.utils.log] DEBUG: Using asyncio event loop: asyncio.unix_events._UnixSelectorEventLoop
2025-03-22 15:49:32 [scrapy.utils.log] DEBUG: Using reactor: twisted.internet.asyncioreactor.AsyncioSelectorReactor
2025-03-22 15:49:32 [scrapy.utils.log] DEBUG: Using asyncio event loop: asyncio.unix_events._UnixSelectorEventLoop
2025-03-22 15:49:32 [scrapy.extensions.telnet] INFO: Telnet Password: fbd2737bfdbad10f
2025-03-22 15:49:32 [scrapy.middleware] INFO: Enabled extensions:
['scrapy.extensions.corestats.CoreStats',
 'scrapy.extensions.telnet.TelnetConsole',
 'scrapy.extensions.memusage.MemoryUsage',
 'scrapy.extensions.logstats.LogStats']
2025-03-22 15:49:32 [scrapy.crawler] INFO: Overridden settings:
{'BOT_NAME': 'books',
 'FEED_EXPORT_ENCODING': 'utf-8',
 'NEWSPIDER_MODULE': 'books.spiders',
 'ROBOTSTXT_OBEY': True,
 'SPIDER_MODULES': ['books.spiders'],
 'TWISTED_REACTOR': 'twisted.internet.asyncioreactor.AsyncioSelectorReactor'}
2025-03-22 15:49:32 [scrapy.middleware] INFO: Enabled downloader middlewares:
['scrapy.downloadermiddlewares.offsite.OffsiteMiddleware',
 'scrapy.downloadermiddlewares.robotstxt.RobotsTxtMiddleware',
 'scrapy.downloadermiddlewares.httpauth.HttpAuthMiddleware',
 'scrapy.downloadermiddlewares.downloadtimeout.DownloadTimeoutMiddleware',
 'scrapy.downloadermiddlewares.defaultheaders.DefaultHeadersMiddleware',
 'scrapy.downloadermiddlewares.useragent.UserAgentMiddleware',
 'scrapy.downloadermiddlewares.retry.RetryMiddleware',
 'scrapy.downloadermiddlewares.redirect.MetaRefreshMiddleware',
 'scrapy.downloadermiddlewares.httpcompression.HttpCompressionMiddleware',
 'scrapy.downloadermiddlewares.redirect.RedirectMiddleware',
 'scrapy.downloadermiddlewares.cookies.CookiesMiddleware',
 'scrapy.downloadermiddlewares.httpproxy.HttpProxyMiddleware',
 'scrapy.downloadermiddlewares.stats.DownloaderStats']
2025-03-22 15:49:32 [scrapy.middleware] INFO: Enabled spider middlewares:
['scrapy.spidermiddlewares.httperror.HttpErrorMiddleware',
 'scrapy.spidermiddlewares.referer.RefererMiddleware',
 'scrapy.spidermiddlewares.urllength.UrlLengthMiddleware',
 'scrapy.spidermiddlewares.depth.DepthMiddleware']
2025-03-22 15:49:32 [scrapy.middleware] INFO: Enabled item pipelines:
[]
2025-03-22 15:49:32 [scrapy.core.engine] INFO: Spider opened
2025-03-22 15:49:32 [scrapy.extensions.logstats] INFO: Crawled 0 pages (at 0 pages/min), scraped 0 items (at 0 items/min)
2025-03-22 15:49:32 [scrapy.extensions.telnet] INFO: Telnet console listening on 127.0.0.1:6023
2025-03-22 15:49:33 [scrapy.core.engine] DEBUG: Crawled (404) <GET https://books.toscrape.com/robots.txt> (referer: None)
2025-03-22 15:49:33 [scrapy.core.engine] DEBUG: Crawled (200) <GET https://books.toscrape.com/> (referer: None)
2025-03-22 15:49:33 [scrapy.core.scraper] ERROR: Spider error processing <GET https://books.toscrape.com/> (referer: None)
Traceback (most recent call last):
  File "/usr/local/lib/python3.9/dist-packages/scrapy/utils/defer.py", line 327, in iter_errback
    yield next(it)
  File "/usr/local/lib/python3.9/dist-packages/scrapy/utils/python.py", line 368, in __next__
    return next(self.data)
  File "/usr/local/lib/python3.9/dist-packages/scrapy/utils/python.py", line 368, in __next__
    return next(self.data)
  File "/usr/local/lib/python3.9/dist-packages/scrapy/core/spidermw.py", line 106, in process_sync
    yield from iterable
  File "/usr/local/lib/python3.9/dist-packages/scrapy/spidermiddlewares/referer.py", line 379, in <genexpr>
    return (self._set_referer(r, response) for r in result)
  File "/usr/local/lib/python3.9/dist-packages/scrapy/core/spidermw.py", line 106, in process_sync
    yield from iterable
  File "/usr/local/lib/python3.9/dist-packages/scrapy/spidermiddlewares/urllength.py", line 57, in <genexpr>
    return (r for r in result if self._filter(r, spider))
  File "/usr/local/lib/python3.9/dist-packages/scrapy/core/spidermw.py", line 106, in process_sync
    yield from iterable
  File "/usr/local/lib/python3.9/dist-packages/scrapy/spidermiddlewares/depth.py", line 54, in <genexpr>
    return (r for r in result if self._filter(r, response, spider))
  File "/usr/local/lib/python3.9/dist-packages/scrapy/core/spidermw.py", line 106, in process_sync
    yield from iterable
  File "/home/User1/books/books/spiders/books.py", line 13, in parse
    item["title"] = book.css("h3 > a:attr(title)").get
  File "/usr/local/lib/python3.9/dist-packages/parsel/selector.py", line 655, in css
    return self.xpath(self._css2xpath(query))
  File "/usr/local/lib/python3.9/dist-packages/parsel/selector.py", line 659, in _css2xpath
    return _ctgroup[type]["_csstranslator"].css_to_xpath(query)
  File "/usr/local/lib/python3.9/dist-packages/parsel/csstranslator.py", line 137, in css_to_xpath
    return super().css_to_xpath(css, prefix)
  File "/usr/local/lib/python3.9/dist-packages/cssselect/xpath.py", line 221, in css_to_xpath
    return " | ".join(
  File "/usr/local/lib/python3.9/dist-packages/cssselect/xpath.py", line 222, in <genexpr>
    self.selector_to_xpath(selector, prefix, translate_pseudo_elements=True)
  File "/usr/local/lib/python3.9/dist-packages/cssselect/xpath.py", line 255, in selector_to_xpath
    xpath = self.xpath(tree)
  File "/usr/local/lib/python3.9/dist-packages/cssselect/xpath.py", line 297, in xpath
    return method(parsed_selector)
  File "/usr/local/lib/python3.9/dist-packages/cssselect/xpath.py", line 308, in xpath_combinedselector
    return method(self.xpath(combined.selector), self.xpath(combined.subselector))
  File "/usr/local/lib/python3.9/dist-packages/cssselect/xpath.py", line 297, in xpath
    return method(parsed_selector)
  File "/usr/local/lib/python3.9/dist-packages/cssselect/xpath.py", line 358, in xpath_function
    raise ExpressionError(f"The pseudo-class :{function.name}() is unknown")
cssselect.xpath.ExpressionError: The pseudo-class :attr() is unknown
2025-03-22 15:49:33 [scrapy.core.engine] INFO: Closing spider (finished)
2025-03-22 15:49:33 [scrapy.statscollectors] INFO: Dumping Scrapy stats:
{'downloader/request_bytes': 448,
 'downloader/request_count': 2,
 'downloader/request_method_count/GET': 2,
 'downloader/response_bytes': 51883,
 'downloader/response_count': 2,
 'downloader/response_status_count/200': 1,
 'downloader/response_status_count/404': 1,
 'elapsed_time_seconds': 1.064591,
 'finish_reason': 'finished',
 'finish_time': datetime.datetime(2025, 3, 22, 14, 49, 33, 520681, tzinfo=datetime.timezone.utc),
 'items_per_minute': None,
 'log_count/DEBUG': 7,
 'log_count/ERROR': 1,
 'log_count/INFO': 10,
 'memusage/max': 42328064,
 'memusage/startup': 42328064,
 'response_received_count': 2,
 'responses_per_minute': None,
 'robotstxt/request_count': 1,
 'robotstxt/response_count': 1,
 'robotstxt/response_status_count/404': 1,
 'scheduler/dequeued': 1,
 'scheduler/dequeued/memory': 1,
 'scheduler/enqueued': 1,
 'scheduler/enqueued/memory': 1,
 'spider_exceptions/ExpressionError': 1,
 'start_time': datetime.datetime(2025, 3, 22, 14, 49, 32, 456090, tzinfo=datetime.timezone.utc)}
2025-03-22 15:49:33 [scrapy.core.engine] INFO: Spider closed (finished)
```




build using webpage:
https://realpython.com/web-scraping-with-scrapy-and-mongodb/
