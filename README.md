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
2025-03-22 16:26:02 [scrapy.utils.log] INFO: Scrapy 2.12.0 started (bot: books)
2025-03-22 16:26:02 [scrapy.utils.log] INFO: Versions: lxml 4.6.3.0, libxml2 2.9.10, cssselect 1.3.0, parsel 1.10.0, w3lib 2.3.1, Twisted 24.11.0, Python 3.9.2 (default, Dec  9 2024, 13:57:34) - [GCC 10.2.1 20210110], pyOpenSSL 25.0.0 (OpenSSL 3.4.1 11 Feb 2025), cryptography 44.0.2, Platform Linux-6.1.21-v8+-aarch64-with-glibc2.31
2025-03-22 16:26:02 [scrapy.addons] INFO: Enabled addons:
[]
2025-03-22 16:26:02 [asyncio] DEBUG: Using selector: EpollSelector
2025-03-22 16:26:02 [scrapy.utils.log] DEBUG: Using reactor: twisted.internet.asyncioreactor.AsyncioSelectorReactor
2025-03-22 16:26:02 [scrapy.utils.log] DEBUG: Using asyncio event loop: asyncio.unix_events._UnixSelectorEventLoop
2025-03-22 16:26:02 [scrapy.utils.log] DEBUG: Using reactor: twisted.internet.asyncioreactor.AsyncioSelectorReactor
2025-03-22 16:26:02 [scrapy.utils.log] DEBUG: Using asyncio event loop: asyncio.unix_events._UnixSelectorEventLoop
2025-03-22 16:26:02 [scrapy.extensions.telnet] INFO: Telnet Password: 92b504eede45e735
2025-03-22 16:26:02 [scrapy.middleware] INFO: Enabled extensions:
['scrapy.extensions.corestats.CoreStats',
 'scrapy.extensions.telnet.TelnetConsole',
 'scrapy.extensions.memusage.MemoryUsage',
 'scrapy.extensions.logstats.LogStats']
2025-03-22 16:26:02 [scrapy.crawler] INFO: Overridden settings:
{'BOT_NAME': 'books',
 'FEED_EXPORT_ENCODING': 'utf-8',
 'NEWSPIDER_MODULE': 'books.spiders',
 'ROBOTSTXT_OBEY': True,
 'SPIDER_MODULES': ['books.spiders'],
 'TWISTED_REACTOR': 'twisted.internet.asyncioreactor.AsyncioSelectorReactor'}
2025-03-22 16:26:02 [scrapy.middleware] INFO: Enabled downloader middlewares:
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
2025-03-22 16:26:02 [scrapy.middleware] INFO: Enabled spider middlewares:
['scrapy.spidermiddlewares.httperror.HttpErrorMiddleware',
 'scrapy.spidermiddlewares.referer.RefererMiddleware',
 'scrapy.spidermiddlewares.urllength.UrlLengthMiddleware',
 'scrapy.spidermiddlewares.depth.DepthMiddleware']
2025-03-22 16:26:02 [scrapy.middleware] INFO: Enabled item pipelines:
[]
2025-03-22 16:26:02 [scrapy.core.engine] INFO: Spider opened
2025-03-22 16:26:02 [scrapy.extensions.logstats] INFO: Crawled 0 pages (at 0 pages/min), scraped 0 items (at 0 items/min)
2025-03-22 16:26:02 [scrapy.extensions.telnet] INFO: Telnet console listening on 127.0.0.1:6023
2025-03-22 16:26:03 [scrapy.core.engine] DEBUG: Crawled (404) <GET https://books.toscrape.com/robots.txt> (referer: None)
2025-03-22 16:26:03 [scrapy.core.engine] DEBUG: Crawled (200) <GET https://books.toscrape.com/> (referer: None)
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/>
{'price': '£51.77',
 'title': 'A Light in the Attic',
 'url': 'catalogue/a-light-in-the-attic_1000/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/>
{'price': '£53.74',
 'title': 'Tipping the Velvet',
 'url': 'catalogue/tipping-the-velvet_999/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/>
{'price': '£50.10',
 'title': 'Soumission',
 'url': 'catalogue/soumission_998/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/>
{'price': '£47.82',
 'title': 'Sharp Objects',
 'url': 'catalogue/sharp-objects_997/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/>
{'price': '£54.23',
 'title': 'Sapiens: A Brief History of Humankind',
 'url': 'catalogue/sapiens-a-brief-history-of-humankind_996/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/>
{'price': '£22.65',
 'title': 'The Requiem Red',
 'url': 'catalogue/the-requiem-red_995/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/>
{'price': '£33.34',
 'title': 'The Dirty Little Secrets of Getting Your Dream Job',
 'url': 'catalogue/the-dirty-little-secrets-of-getting-your-dream-job_994/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/>
{'price': '£17.93',
 'title': 'The Coming Woman: A Novel Based on the Life of the Infamous '
          'Feminist, Victoria Woodhull',
 'url': 'catalogue/the-coming-woman-a-novel-based-on-the-life-of-the-infamous-feminist-victoria-woodhull_993/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/>
{'price': '£22.60',
 'title': 'The Boys in the Boat: Nine Americans and Their Epic Quest for Gold '
          'at the 1936 Berlin Olympics',
 'url': 'catalogue/the-boys-in-the-boat-nine-americans-and-their-epic-quest-for-gold-at-the-1936-berlin-olympics_992/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/>
{'price': '£52.15',
 'title': 'The Black Maria',
 'url': 'catalogue/the-black-maria_991/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/>
{'price': '£13.99',
 'title': 'Starving Hearts (Triangular Trade Trilogy, #1)',
 'url': 'catalogue/starving-hearts-triangular-trade-trilogy-1_990/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/>
{'price': '£20.66',
 'title': "Shakespeare's Sonnets",
 'url': 'catalogue/shakespeares-sonnets_989/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/>
{'price': '£17.46',
 'title': 'Set Me Free',
 'url': 'catalogue/set-me-free_988/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/>
{'price': '£52.29',
 'title': "Scott Pilgrim's Precious Little Life (Scott Pilgrim #1)",
 'url': 'catalogue/scott-pilgrims-precious-little-life-scott-pilgrim-1_987/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/>
{'price': '£35.02',
 'title': 'Rip it Up and Start Again',
 'url': 'catalogue/rip-it-up-and-start-again_986/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/>
{'price': '£57.25',
 'title': 'Our Band Could Be Your Life: Scenes from the American Indie '
          'Underground, 1981-1991',
 'url': 'catalogue/our-band-could-be-your-life-scenes-from-the-american-indie-underground-1981-1991_985/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/>
{'price': '£23.88', 'title': 'Olio', 'url': 'catalogue/olio_984/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/>
{'price': '£37.59',
 'title': 'Mesaerion: The Best Science Fiction Stories 1800-1849',
 'url': 'catalogue/mesaerion-the-best-science-fiction-stories-1800-1849_983/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/>
{'price': '£51.33',
 'title': 'Libertarianism for Beginners',
 'url': 'catalogue/libertarianism-for-beginners_982/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/>
{'price': '£45.17',
 'title': "It's Only the Himalayas",
 'url': 'catalogue/its-only-the-himalayas_981/index.html'}
2025-03-22 16:26:03 [book] INFO: Navigating to new page URL: https://books.toscrape.com/catalogue/page-2.html.
2025-03-22 16:26:03 [scrapy.core.engine] DEBUG: Crawled (200) <GET https://books.toscrape.com/catalogue/page-2.html> (referer: https://books.toscrape.com/)
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-2.html>
{'price': '£12.84', 'title': 'In Her Wake', 'url': 'in-her-wake_980/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-2.html>
{'price': '£37.32',
 'title': 'How Music Works',
 'url': 'how-music-works_979/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-2.html>
{'price': '£30.52',
 'title': 'Foolproof Preserving: A Guide to Small Batch Jams, Jellies, '
          'Pickles, Condiments, and More: A Foolproof Guide to Making Small '
          'Batch Jams, Jellies, Pickles, Condiments, and More',
 'url': 'foolproof-preserving-a-guide-to-small-batch-jams-jellies-pickles-condiments-and-more-a-foolproof-guide-to-making-small-batch-jams-jellies-pickles-condiments-and-more_978/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-2.html>
{'price': '£25.27',
 'title': 'Chase Me (Paris Nights #2)',
 'url': 'chase-me-paris-nights-2_977/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-2.html>
{'price': '£34.53', 'title': 'Black Dust', 'url': 'black-dust_976/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-2.html>
{'price': '£54.64',
 'title': 'Birdsong: A Story in Pictures',
 'url': 'birdsong-a-story-in-pictures_975/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-2.html>
{'price': '£22.50',
 'title': "America's Cradle of Quarterbacks: Western Pennsylvania's Football "
          'Factory from Johnny Unitas to Joe Montana',
 'url': 'americas-cradle-of-quarterbacks-western-pennsylvanias-football-factory-from-johnny-unitas-to-joe-montana_974/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-2.html>
{'price': '£53.13',
 'title': 'Aladdin and His Wonderful Lamp',
 'url': 'aladdin-and-his-wonderful-lamp_973/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-2.html>
{'price': '£40.30',
 'title': 'Worlds Elsewhere: Journeys Around Shakespeare’s Globe',
 'url': 'worlds-elsewhere-journeys-around-shakespeares-globe_972/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-2.html>
{'price': '£44.18',
 'title': 'Wall and Piece',
 'url': 'wall-and-piece_971/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-2.html>
{'price': '£17.66',
 'title': 'The Four Agreements: A Practical Guide to Personal Freedom',
 'url': 'the-four-agreements-a-practical-guide-to-personal-freedom_970/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-2.html>
{'price': '£31.05',
 'title': 'The Five Love Languages: How to Express Heartfelt Commitment to '
          'Your Mate',
 'url': 'the-five-love-languages-how-to-express-heartfelt-commitment-to-your-mate_969/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-2.html>
{'price': '£23.82',
 'title': 'The Elephant Tree',
 'url': 'the-elephant-tree_968/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-2.html>
{'price': '£36.89',
 'title': 'The Bear and the Piano',
 'url': 'the-bear-and-the-piano_967/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-2.html>
{'price': '£15.94',
 'title': "Sophie's World",
 'url': 'sophies-world_966/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-2.html>
{'price': '£33.29', 'title': 'Penny Maybe', 'url': 'penny-maybe_965/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-2.html>
{'price': '£18.02',
 'title': 'Maude (1883-1993):She Grew Up with the country',
 'url': 'maude-1883-1993she-grew-up-with-the-country_964/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-2.html>
{'price': '£19.63',
 'title': 'In a Dark, Dark Wood',
 'url': 'in-a-dark-dark-wood_963/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-2.html>
{'price': '£52.22',
 'title': 'Behind Closed Doors',
 'url': 'behind-closed-doors_962/index.html'}
2025-03-22 16:26:03 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-2.html>
{'price': '£33.63',
 'title': "You can't bury them all: Poems",
 'url': 'you-cant-bury-them-all-poems_961/index.html'}
2025-03-22 16:26:03 [book] INFO: Navigating to new page URL: https://books.toscrape.com/catalogue/page-3.html.
2025-03-22 16:26:04 [scrapy.core.engine] DEBUG: Crawled (200) <GET https://books.toscrape.com/catalogue/page-3.html> (referer: https://books.toscrape.com/catalogue/page-2.html)
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-3.html>
{'price': '£57.31',
 'title': 'Slow States of Collapse: Poems',
 'url': 'slow-states-of-collapse-poems_960/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-3.html>
{'price': '£26.41',
 'title': 'Reasons to Stay Alive',
 'url': 'reasons-to-stay-alive_959/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-3.html>
{'price': '£47.61',
 'title': 'Private Paris (Private #10)',
 'url': 'private-paris-private-10_958/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-3.html>
{'price': '£23.11',
 'title': '#HigherSelfie: Wake Up Your Life. Free Your Soul. Find Your Tribe.',
 'url': 'higherselfie-wake-up-your-life-free-your-soul-find-your-tribe_957/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-3.html>
{'price': '£45.07',
 'title': 'Without Borders (Wanderlove #1)',
 'url': 'without-borders-wanderlove-1_956/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-3.html>
{'price': '£31.77',
 'title': 'When We Collided',
 'url': 'when-we-collided_955/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-3.html>
{'price': '£50.27',
 'title': 'We Love You, Charlie Freeman',
 'url': 'we-love-you-charlie-freeman_954/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-3.html>
{'price': '£14.27',
 'title': 'Untitled Collection: Sabbath Poems 2014',
 'url': 'untitled-collection-sabbath-poems-2014_953/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-3.html>
{'price': '£44.18',
 'title': 'Unseen City: The Majesty of Pigeons, the Discreet Charm of Snails & '
          'Other Wonders of the Urban Wilderness',
 'url': 'unseen-city-the-majesty-of-pigeons-the-discreet-charm-of-snails-other-wonders-of-the-urban-wilderness_952/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-3.html>
{'price': '£18.78',
 'title': 'Unicorn Tracks',
 'url': 'unicorn-tracks_951/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-3.html>
{'price': '£25.52',
 'title': 'Unbound: How Eight Technologies Made Us Human, Transformed Society, '
          'and Brought Our World to the Brink',
 'url': 'unbound-how-eight-technologies-made-us-human-transformed-society-and-brought-our-world-to-the-brink_950/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-3.html>
{'price': '£16.28',
 'title': 'Tsubasa: WoRLD CHRoNiCLE 2 (Tsubasa WoRLD CHRoNiCLE #2)',
 'url': 'tsubasa-world-chronicle-2-tsubasa-world-chronicle-2_949/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-3.html>
{'price': '£31.12',
 'title': 'Throwing Rocks at the Google Bus: How Growth Became the Enemy of '
          'Prosperity',
 'url': 'throwing-rocks-at-the-google-bus-how-growth-became-the-enemy-of-prosperity_948/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-3.html>
{'price': '£19.49',
 'title': 'This One Summer',
 'url': 'this-one-summer_947/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-3.html>
{'price': '£17.27', 'title': 'Thirst', 'url': 'thirst_946/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-3.html>
{'price': '£19.09',
 'title': 'The Torch Is Passed: A Harding Family Story',
 'url': 'the-torch-is-passed-a-harding-family-story_945/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-3.html>
{'price': '£56.13',
 'title': 'The Secret of Dreadwillow Carse',
 'url': 'the-secret-of-dreadwillow-carse_944/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-3.html>
{'price': '£56.41',
 'title': 'The Pioneer Woman Cooks: Dinnertime: Comfort Classics, Freezer '
          'Food, 16-Minute Meals, and Other Delicious Ways to Solve Supper!',
 'url': 'the-pioneer-woman-cooks-dinnertime-comfort-classics-freezer-food-16-minute-meals-and-other-delicious-ways-to-solve-supper_943/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-3.html>
{'price': '£56.50',
 'title': 'The Past Never Ends',
 'url': 'the-past-never-ends_942/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-3.html>
{'price': '£45.22',
 'title': 'The Natural History of Us (The Fine Art of Pretending #2)',
 'url': 'the-natural-history-of-us-the-fine-art-of-pretending-2_941/index.html'}
2025-03-22 16:26:04 [book] INFO: Navigating to new page URL: https://books.toscrape.com/catalogue/page-4.html.
^C2025-03-22 16:26:04 [scrapy.crawler] INFO: Received SIGINT, shutting down gracefully. Send again to force 
2025-03-22 16:26:04 [scrapy.core.engine] INFO: Closing spider (shutdown)
2025-03-22 16:26:04 [scrapy.core.engine] DEBUG: Crawled (200) <GET https://books.toscrape.com/catalogue/page-4.html> (referer: https://books.toscrape.com/catalogue/page-3.html)
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-4.html>
{'price': '£38.16',
 'title': 'The Nameless City (The Nameless City #1)',
 'url': 'the-nameless-city-the-nameless-city-1_940/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-4.html>
{'price': '£54.11',
 'title': 'The Murder That Never Was (Forensic Instincts #5)',
 'url': 'the-murder-that-never-was-forensic-instincts-5_939/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-4.html>
{'price': '£42.96',
 'title': "The Most Perfect Thing: Inside (and Outside) a Bird's Egg",
 'url': 'the-most-perfect-thing-inside-and-outside-a-birds-egg_938/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-4.html>
{'price': '£23.89',
 'title': 'The Mindfulness and Acceptance Workbook for Anxiety: A Guide to '
          'Breaking Free from Anxiety, Phobias, and Worry Using Acceptance and '
          'Commitment Therapy',
 'url': 'the-mindfulness-and-acceptance-workbook-for-anxiety-a-guide-to-breaking-free-from-anxiety-phobias-and-worry-using-acceptance-and-commitment-therapy_937/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-4.html>
{'price': '£16.77',
 'title': 'The Life-Changing Magic of Tidying Up: The Japanese Art of '
          'Decluttering and Organizing',
 'url': 'the-life-changing-magic-of-tidying-up-the-japanese-art-of-decluttering-and-organizing_936/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-4.html>
{'price': '£20.59',
 'title': 'The Inefficiency Assassin: Time Management Tactics for Working '
          'Smarter, Not Longer',
 'url': 'the-inefficiency-assassin-time-management-tactics-for-working-smarter-not-longer_935/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-4.html>
{'price': '£37.13',
 'title': 'The Gutsy Girl: Escapades for Your Life of Epic Adventure',
 'url': 'the-gutsy-girl-escapades-for-your-life-of-epic-adventure_934/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-4.html>
{'price': '£56.06',
 'title': 'The Electric Pencil: Drawings from Inside State Hospital No. 3',
 'url': 'the-electric-pencil-drawings-from-inside-state-hospital-no-3_933/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-4.html>
{'price': '£58.11',
 'title': 'The Death of Humanity: and the Case for Life',
 'url': 'the-death-of-humanity-and-the-case-for-life_932/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-4.html>
{'price': '£49.05',
 'title': 'The Bulletproof Diet: Lose up to a Pound a Day, Reclaim Energy and '
          'Focus, Upgrade Your Life',
 'url': 'the-bulletproof-diet-lose-up-to-a-pound-a-day-reclaim-energy-and-focus-upgrade-your-life_931/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-4.html>
{'price': '£40.76',
 'title': 'The Art Forger',
 'url': 'the-art-forger_930/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-4.html>
{'price': '£19.73',
 'title': 'The Age of Genius: The Seventeenth Century and the Birth of the '
          'Modern Mind',
 'url': 'the-age-of-genius-the-seventeenth-century-and-the-birth-of-the-modern-mind_929/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-4.html>
{'price': '£32.24',
 'title': "The Activist's Tao Te Ching: Ancient Advice for a Modern Revolution",
 'url': 'the-activists-tao-te-ching-ancient-advice-for-a-modern-revolution_928/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-4.html>
{'price': '£41.83',
 'title': 'Spark Joy: An Illustrated Master Class on the Art of Organizing and '
          'Tidying Up',
 'url': 'spark-joy-an-illustrated-master-class-on-the-art-of-organizing-and-tidying-up_927/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-4.html>
{'price': '£39.58', 'title': 'Soul Reader', 'url': 'soul-reader_926/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-4.html>
{'price': '£39.25', 'title': 'Security', 'url': 'security_925/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-4.html>
{'price': '£25.02',
 'title': 'Saga, Volume 6 (Saga (Collected Editions) #6)',
 'url': 'saga-volume-6-saga-collected-editions-6_924/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-4.html>
{'price': '£51.04',
 'title': 'Saga, Volume 5 (Saga (Collected Editions) #5)',
 'url': 'saga-volume-5-saga-collected-editions-5_923/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-4.html>
{'price': '£19.83',
 'title': 'Reskilling America: Learning to Labor in the Twenty-First Century',
 'url': 'reskilling-america-learning-to-labor-in-the-twenty-first-century_922/index.html'}
2025-03-22 16:26:04 [scrapy.core.scraper] DEBUG: Scraped from <200 https://books.toscrape.com/catalogue/page-4.html>
{'price': '£50.40',
 'title': 'Rat Queens, Vol. 3: Demons (Rat Queens (Collected Editions) #11-15)',
 'url': 'rat-queens-vol-3-demons-rat-queens-collected-editions-11-15_921/index.html'}
2025-03-22 16:26:04 [book] INFO: Navigating to new page URL: https://books.toscrape.com/catalogue/page-5.html.
2025-03-22 16:26:04 [scrapy.statscollectors] INFO: Dumping Scrapy stats:
{'downloader/request_bytes': 1324,
 'downloader/request_count': 5,
 'downloader/request_method_count/GET': 5,
 'downloader/response_bytes': 207441,
 'downloader/response_count': 5,
 'downloader/response_status_count/200': 4,
 'downloader/response_status_count/404': 1,
 'elapsed_time_seconds': 1.932438,
 'finish_reason': 'shutdown',
 'finish_time': datetime.datetime(2025, 3, 22, 15, 26, 4, 602716, tzinfo=datetime.timezone.utc),
 'item_scraped_count': 80,
 'items_per_minute': None,
 'log_count/DEBUG': 90,
 'log_count/INFO': 15,
 'memusage/max': 42176512,
 'memusage/startup': 42176512,
 'request_depth_max': 4,
 'response_received_count': 5,
 'responses_per_minute': None,
 'robotstxt/request_count': 1,
 'robotstxt/response_count': 1,
 'robotstxt/response_status_count/404': 1,
 'scheduler/dequeued': 4,
 'scheduler/dequeued/memory': 4,
 'scheduler/enqueued': 5,
 'scheduler/enqueued/memory': 5,
 'start_time': datetime.datetime(2025, 3, 22, 15, 26, 2, 670278, tzinfo=datetime.timezone.utc)}
2025-03-22 16:26:04 [scrapy.core.engine] INFO: Spider closed (shutdown)
```




build using webpage:
https://realpython.com/web-scraping-with-scrapy-and-mongodb/
