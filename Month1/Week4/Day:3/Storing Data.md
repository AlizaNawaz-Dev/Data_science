# Data Storage:
**scraping multiple titles, authors and quotes.**
``` python
import scrapy

class QuoteSpider(scrapy.Spider):

    name= "Quote"
    start_urls=["https://quotes.toscrape.com/"]

    def parse(self,response):

        all_div_quotes=response.css("div.quote")
        
        for quotes in all_div_quotes:

            title= quotes.css("span.text::text").extract()
            author= quotes.css(".author::text").extract()
            tags= quotes.css(".tag::text").extract()

            yield {"Title" : title,
                   "Author": author,
                   "Tags"  : tags
                   }
```

### Creating Items/Containers:  
Inside items.py file  

name = scrapy.Field()  (where name is container for info scraped inside name)  
``` python
import scrapy


class QuoteItem(scrapy.Item):

     title = scrapy.Field()
     author = scrapy.Field()
     tags= scrapy.Field()
```
Using these containers inside our spider file.  
1- import this item file in spider file.
   - from ..items import QuoteItem      (Quoteitem is class containing items)  

2- Inside parse method create instance of imported class.  
   - items(objectname)=AmazonItem()(class)  

3- We have to store scraped data in individual containers.  
   - items["name"]=name
``` python
import scrapy

from ..items import QuoteItem

class QuoteSpider(scrapy.Spider):

    name= "Quote"
    start_urls=["https://quotes.toscrape.com/"]

    def parse(self,response):

        items=QuoteItem()

        all_div_quotes=response.css("div.quote")
        for quotes in all_div_quotes:

            title= quotes.css("span.text::text").extract()
            author= quotes.css(".author::text").extract()
            tags= quotes.css(".tag::text").extract()
            
            items["title"] = title
            items["author"] =author
            items["tags"] = tags
            
            yield items
  ```
# Storing scraped Data:
- Now for storing scraped data in xml,csv and json file format.   

- We can give different extensions to file as required(.json,.xml,.csv).  

- scrapy crawl spider_name -o file_name.csv
``` python
scrapy crawl Quote -o items.csv        # for Stoing data in csv file format.

scrapy crawl Quote -o items.xml        # for Stoing data in xml file format.

scrapy crawl Quote -o items.json        # for Stoing data in json file format.
```

# Pipelines:
- 
Activate pipelines:
uncommment code given below(already given inside settings.py(comes with scrapy package) file)
``` python
ITEM_PIPELINES = {
   'quote.pipelines.QuotePipeline': 300,
}
```

# Basics of sqlite3:
Following steps need to be followed for data storage in sqlite3.
1- import sqlite3  
2- Create connection to the database.  
    - conn=sqlite3.connect("my_db.db")     
    - **my_db.db** is name of database (if file doesn't exsist then it will be created using .db extension) 

