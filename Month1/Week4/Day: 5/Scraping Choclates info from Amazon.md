## Bypassing restrictions:
- Some websites disallow Scraping large amount of data multiple times from their websites.  

- We can bypass those restrictions using methods like useragents and proxies.   
     - **UserAgents**: (rotating different browser identitites)  
                     • For changing our browsers identity 
                      In  **settings.py** change the link of your user agent with the following link.  
                       
                       USER_AGENT =Mozilla/5.0 (compatible; Googlebot/2.1; +https://www.google.com/bot.html)'  
                       
         • Alternative to above code is:  
                     In **settings.py**file paste this code  
```python
     DOWNLOADER_MIDDLEWARES = {
    'scrapy.downloadermiddlewares.useragent.UserAgentMiddleware': None,
    
    'scrapy_user_agents.middlewares.RandomUserAgentMiddleware': 400,
}
```
                       
  **Proxies** :(rotating different IP addresses)
``` python
DOWNLOADER_MIDDLEWARES = {
    # ...
    'scrapy_proxy_pool.middlewares.ProxyPoolMiddleware': 610,
    'scrapy_proxy_pool.middlewares.BanDetectionMiddleware': 620,
    # ...
}
```
## Scraping Choclates price,ratings,imagelink and quantity from Amazon:
- Following code will scrape Choclates price,ratings,imagelink and quantity from all available pages in selected section of amazon.  
- amazon_spider.py
```python
import scrapy
from ..items import AmazonItem


class AmazonSpiderSpider(scrapy.Spider):
    name = 'amazon_spider'
    page_number=2
    start_urls = [
        'https://www.amazon.com/s?k=chocolates&crid=2RRM21AZHD1PP&sprefix=chocolates%2Caps%2C296&ref=nb_sb_noss_1']

    def parse(self, response):
        items = AmazonItem()

        product_ratings = response.css(".a-icon-alt::text").extract()
        product_price = response.css(".a-size-base.s-underline-text").css("::text").extract()
        product_quantity = response.css(".a-color-information , .widgetId\=search-results_24 .a-text-normal").css( "::text").extract()
        product_image = response.css(".s-image::attr(src)").extract()

        items["product_ratings"] = product_ratings
        items["product_price"] = product_price
        items["product_quantity"] = product_quantity
        items["product_image"] = product_image

        yield items

        next_page="https://www.amazon.com/sk=chocolates&page="+str(AmazonSpiderSpider.page_number)+"&crid=2RRM21AZHD1PP&qid=1663939819&sprefix=chocolates%2Caps%2C296&ref=g_2"
        if AmazonSpiderSpider.page_number <=7:
            AmazonSpiderSpider.page_number +=1
            yield response.follow(next_page,callback= self.parse)
 ```

- In items.py file:
``` python 
import scrapy


class AmazonItem(scrapy.Item):
    # define the fields for your item here like:
    product_ratings = scrapy.Field()
    product_price = scrapy.Field()
    product_quantity = scrapy.Field()
    product_image = scrapy.Field()
 ```
 - In pipelines.py file(For storing scraped data in sqlite3)
 ```python
 import sqlite3

class AmazonPipeline(object):
    def __int__(self):
        self.create_connection()
        self.create_table()

    def create_connection(self):
        self.conn = sqlite3.connect('choclates.db')
        self.curr = self.conn.cursor()

    def create_table(self):
        self.curr.execute("""DROP TABLE IF EXISTS INFO""")
        self.curr.execute("""create table INFO (Product_ratings float, 
                Product_price float,
                C float ,
                product_image text)""")
    def process_item(self, item, spider):
        self.store_db(item)
        return item
    def store_db(self,item):
        self.curr.execute("""insert into INFO values(?,?,?,?)""", (
            item["Product_ratings"] [0],
            item["Product_price"] [0],
            item[" Product_price"] [0],
            item[" Product_image"] [0],
        ))
        self.conn.commit()
 ```
