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
