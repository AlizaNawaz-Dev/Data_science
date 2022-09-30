# Storing Scraped Data in sqlite3:
In pipeline.py file
``` python
import sqlite3

class QuotePipeline:

    def __int__(self):
    
        self.create_connection()
        self.create_table()
    def create_connection(self):
    
        self.conn=sqlite3.connect('quotes.db')
        self.curr=self.conn.cursor()
    def create_table(self):
    
        self.curr.execute("""DROP TABLE IF EXISTS INFO""")
        self.curr.execute("""create table INFO (Title text, 
                                                Author text,
                                                Tag text)""")
    def process_item(self, item, spider):
    
        self.store_db(item)
        return item
    def store_db(self,item):
    
        self.curr.execute("""insert into INFO values(?,?,?)""",(
                                               item["title"][0],
                                               item["author"][0],
                                               item["tags"][0]
        ))
        self.conn.commit()
```

# Storing Scraped Data in mysql:
``` python
import mysql.connector

class QuotePipeline:

    def __int__(self):
        self.create_connection()
        self.create_table()

    def create_connection(self):
        self.conn = mysql.connecter.connect(host='localhost',
                                            user='root',
                                            password='aliza123',
                                            database='myquotes'
                                            )
        self.curr = self.conn.cursor()

    def create_table(self):
    
        self.curr.execute("""DROP TABLE IF EXISTS quotes_tb""")
        self.curr.execute("""create table quotes_tb (Title text, 
                                                     Author text,
                                                     Tag text)""")

    def process_item(self, item, spider):
    
        self.store_db(item)
        return item

    def store_db(self, item):
    
        self.curr.execute("""insert into quotes_tb values(%s,%s,%s)""", (
                                                        item["title"][0],
                                                        item["author"][0],
                                                        item["tags"][0]
        ))
        self.conn.commit()
```
# Storing Scraped Data in MongoDB:
``` python
import pymongo

inside class

def __init__()self:

	self.conn=pymongo.Mongoclient('localhost',27017)                      # 27101=portnumber present in mongo software

db=self.conn["my_db"]                                                   # creating database

self.collection=db["my_table"]                                          #creating table

def process_item(self, item, spider): 
	self.collection.insert(dic(item))                                     #inserting into table

```
