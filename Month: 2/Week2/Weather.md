# Weather:
``` python
from tkinter import *
from PIL import ImageTk, Image
import requests
import json

root = Tk()
root.title('Learn to code')
root.iconbitmap('C:\gui\win.ico')
root.geometry("600x100")


def zipLookup():
    #     zip.get()
    #     zipLabel=Label(root,text=zip.get())
    #     zipLabel.grid(row=1, column=0, columnspan=2)
    try:
        api_requests = requests.get(
            "http://www.airnowapi.org/aq/observation/zipCode/current/?format=application/json&zipCode=" + zip.get() + "&distance=5&API_KEY=96A38DFD-5C56-4740-AD99-E38C0C855A1B")
        api = json.loads(api_requests.content)
        city = api[0]['ReportingArea']
        quality = api[0]['AQI']
        category = api[0]['Category']['Name']
        if category == "Good":
            weather_color = "#0C0"
        elif category == "Moderate":
            weather_color = "#FFFF00"
        elif category == "Unhealthy for Sensitive Groups":
            weather_color = "#ff9900"
        elif category == "Unhealthy":
            weather_color = "#FF0000"
        elif category == "Very Unhealthy":
            weather_color = "#990066"
        elif category == "Hazardous":
            weather_color = "#660000"
        root.configure(background=weather_color)
        myLabel = Label(root, text=city + " Air Quality " + str(quality) + " " + category, font=("Helvetica", 20),
                        background=weather_color)
        myLabel.grid(row=1, column=0, columnspan=2)
    except Exception as e:
        api = "Error..."


zip = Entry(root)
zip.grid(row=0, column=0, sticky=W + E + N + S)
Btn = Button(root, text="Lookup Zipcode", command=zipLookup).grid(row=0, column=1, sticky=W + E + N + S)

root.mainloop()
```
