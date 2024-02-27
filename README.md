# **Flipkart Mi Mobiles Web Scraping**

### **Overview**

This project involves web scraping Mi mobiles information from Flipkart using Jupyter Notebook. The goal is to extract details such as the name, price, and rating of Mi mobiles from multiple pages on the Flipkart website.

### **Tools and Libraries Used:**

**Pandas**: Used for data manipulation and creating a structured dataset.

**BeautifulSoup (bs4)**: Employed for parsing HTML and extracting relevant information from web pages.

### **Workflow:**

**URL Generation:**

Constructed the URLs for Mi mobiles on Flipkart to facilitate scraping across multiple pages.

**For Loop for Scraping:**

Implemented a for loop to iterate through a specified number of pages (up to 20) to gather data.

**HTML Parsing:**

Utilized BeautifulSoup to parse the HTML content of each page and extract information about Mi mobiles.

**Data Storage:**

Employed Pandas to organize the extracted data into a structured dataset, making it easy to analyze and manipulate.

**Output:**

The final output is a Pandas DataFrame containing Mi mobile details, including name, price, and rating.


**code**

!pip install pandas
!pip install requests
!pip install bs4

import pandas as pd
import requests
from bs4 import BeautifulSoup

name = []
price = []
rating = []

for i in range(1, 5):
    url = 'https://www.flipkart.com/mobiles/mi~brand/pr?sid=tyy%2C4io&otracker=nmenu_sub_Electronics_0_Mi&page=' + str(i)

    req = requests.get(url)
    req.text

    soup = BeautifulSoup(req.text, 'html.parser')

    product_name = soup.find_all("div", attrs={"class": "_4rR01T"})
    product_price = soup.find_all("div", attrs={"class": "_30jeq3 _1_WHN1"})
    product_rating = soup.find_all("div", attrs={"class": "_3LWZlK"})

    for x, y, z in zip(product_name, product_price, product_rating):
        name.append(x.text)
        price.append(y.text)
        rating.append(z.text)

print(len(name))
print(len(price))
print(len(rating))

df = pd.DataFrame({'product_name': name, 'product_price': price, 'product_rating': rating})
print(df)
