# Scraping Mutliple Pages:
**Steps:**  
(Website page indexing based on **next** keyword)  

1- Find next button.  

2- Find link to that other pages using css selector.  

3- Check that where pages are ending (Last page of website).

4- Write this code in quotes_spider file outside for loop.  

``` python
next_page=response.css("li.next a::attr(href)").get()

        if next_page is not None:
            yield response.follow(next_page,callback=self.parse)
```
**Steps:**  
(Website page indexing based on **numbers**(1,2,3) )  

1- Create new variable page_number and initialize it inside quotes_spider file.  

2- Inside for loop create a  new variable next_page followed by a current page link of website.  
    •  **page_number**=2  
    
3- Use page_number variable as page index inside link like this  
    •  **next_page='https://quotes.toscrape.com/page/',QuoteSpider.page_number,'/'**
 
4- Ater this write the following code
``` python
next_page='https://quotes.toscrape.com/page/',QuoteSpider.page_number,'/'
        if QuoteSpider.page_number <11:
            QuoteSpider.page_number+=1
            yield response.follow(next_page,callback=self.parse)
```
