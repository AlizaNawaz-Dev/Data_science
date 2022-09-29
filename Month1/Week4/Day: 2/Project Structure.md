# Scraping Title of a Website:

## Virtual Enviorment:
- A tool to create isolated Python environments. 

- It also gives the ability to isolate Python projects from system's installed Python(one which is installed as part of our operating system).  

**Why virtual enviorment is nessecary for scraping?**  
- It will ensure required libraries are there just for our Python web scraper and not for your system.  

- If we install packages to our operating system these packages will mix with the system-relevant packages.  

- So **Venv** isolates Python installs and associated pip packages and make them independent of those provided by the system or used by other projects.  

- Projects might require a different version of an external library than another one and if we install two different versions of the same package into our global Python environment, the second installation overwrites the first one.  

### Creating Virtual Envoirment:
**Create:-**
``` python 
python -m venv venv
```
**Activate:-**
``` python
venv\Scripts\activate
```

###  css selectors:
- Tell the browser which HTML elements should be selected. 

- Enables to target particular HTML elements(type ,class and ids).  
      

## Scraping Title of website(Using scrapy):

1- Create Virtual enviorment.  

2- Install Scrapy.
   - In terminal
``` python
pip install scrapy

pip install os-scrapy
```

### Starting Project:
1- For starting project go to terminal and write **scrapy startproject project_name**(it will create folder with that project_name inside our main project)  

2- cd project_name (to get into project's sub directory)
``` python
scrapy startproject scraping_title

cd scraping_title
```
### Creating Spider:
1- scrapy genspider spider_name  website
```python
scrapy genspider amazon_spider amazon.com
```
Now our spider file has been created inside spider folder named **amazon_spider**.  

### Scraping Title:
In amazon_spider file.  
   - Inside **start_urls** list paste link of url you want to scrape
   - start_urls = ['https://quotes.toscrape.com/']
   - Extract the required information using css selectors inside parse method.  
   
``` python 
import scrapy

class AmazonSpider(scrapy.Spider):

    name= "Choclates"
    
    start_urls=["https://quotes.toscrape.com/"]

    def parse(self,response):
    
	title=response.css("title::text").extract()
```
### Running scrapy crawler:
In terminal: inside sub-directory(cd project_name)   
**scrapy crawl spider_name**
``` python
scrapy crawl quotes
```
