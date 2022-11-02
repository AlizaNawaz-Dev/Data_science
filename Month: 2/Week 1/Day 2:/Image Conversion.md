# Converting Images:
``` python
from PIL import Image
import glob
print(glob.glob('*.png'))
for file in glob.glob("*.png"):
    im=Image.open(file)
    rgb_im=im.convert('RGB')
    rgb_im.save(file.replace("png","jpg"),quality=95)
import os
for file in glob.glob("*.png"):
    os.remove(file)
```

# Scrapping Using BeautifulSoup:
``` python
import requests
import smtplib
import datetime
from bs4 import BeautifulSoup 
from email.mime.multipart import MIMEMultipart
from email.mime.text import MIMEText

now=datetime.datetime.now()
content=''
def extract_news(url):
    print('Extracting Hacker News Stories...')
    cnt = ''
    cnt +=('<b>HN Top Stories:</b>\n'+'<br>'+'-'*50+'<br>')
    response = requests.get(url)
    content = response.content
    soup = BeautifulSoup(content,'html.parser')
    for i,tag in enumerate(soup.find_all('td',attrs={'class':'title','valign':''})):
        cnt += ((str(i+1)+' :: '+ '<a href="' + tag.a.get('href') + '">' + tag.text + '</a>' + "\n" + '<br>') if tag.text!='More' else '')
        #print(tag.prettify) #find_all('span',attrs={'class':'sitestr'}))
    return(cnt)
cnt=extract_news('https://news.ycombinator.com/')
content+=cnt
content+=('<br>----<br>')
content+=('<br><br> END OF MESSAGE')
print("composing email...........")
SERVER='smtp.gmail.com'
PORT=587
FROM='aliza7@gmail.com'
TO='aliza7@gmail.com'
PASS='hello123'
msg=MIMEMultipart()
msg['Subject']='Top News STORIES HN [Automated Email]'+' '+str(now.day)+'-'+str(now.month)+'-'+str(now.year)
msg['From']=FROM
msg['To']=TO
msg.attach(MIMEText(content,'html'))
print('Initializing server')
server=smtplib.SMTP(SERVER,PORT)
server.set_debuglevel(1)
server.ehlo()
server.starttls()
server.login(FROM,PASS)
server.sendmail(FROM,TO,msg.as_string())
print('EMAIL SENT.......')
server.quit()
```
