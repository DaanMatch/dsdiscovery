# Phase 2: Gathering Additional data

Gather additional data through web scraping and automate the process using GitHub Actions. The collected data will be uploaded to pgAdmin, where an entity-relationship (ER) diagram will be created to visualize the structure and relationships of the data. The ER diagram will help identify what's needed for data transformation.

```{admonition} General process for web scraping
:class: tip
1. **Identify the data to be extracted:** Determine what data you want to extract from the website, such as product prices, reviews, or images.
2. **Find the URLs to scrape:** Identify the URLs of the web pages containing the data you want to extract. This may involve navigating through multiple pages or categories.
3. **Inspect the HTML:** Use your web browser's developer tools to inspect the HTML structure of the web pages and identify the HTML tags and attributes that contain the data you want to extract.
4. **Send HTTP requests:** Use a programming language or web scraping tool to send HTTP requests to the URLs of the web pages and retrieve the HTML content.
5. **Parse the HTML:** Use an HTML parser or web scraping library to extract the relevant data from the HTML content. This may involve searching for specific HTML tags or attributes, or using regular expressions to extract patterns of text.
6. **Store the data:** Save the extracted data in a format such as CSV or JSON, or store it in a database for further analysis.
Handle errors and exceptions: Implement error handling and exception handling to deal with cases where the website is unavailable, the data is not in the expected format, or the scraping process is interrupted.
```

```{admonition} Popular Webscraping Libraries
:class: dropdown
1. **BeautifulSoup:** BeautifulSoup is a Python library used for web scraping purposes to pull the data out of HTML and XML files. It creates a parse tree from page source code that can be used to extract data in a hierarchical and more readable manner.
2. **Scrapy:** Scrapy is an open-source and collaborative web crawling framework for Python. It is used to extract the data from websites and stores it in structured data format such as CSV, JSON or XML.
3. **Selenium:** Selenium is a web testing tool that can also be used for web scraping. It can automate web browsers and simulate user interactions with web pages, which can be useful for scraping dynamic websites.
4. **Requests:** Requests is a simple and elegant Python library used for making HTTP requests to websites. It can be used to download HTML pages or other data from websites, which can then be parsed using other libraries such as BeautifulSoup.
5. **Lxml:** Lxml is a Python library for processing XML and HTML documents. It provides a fast and efficient way to parse and manipulate XML and HTML data, which can be useful for web scraping.
6. **PyQuery:** PyQuery is a Python library used for web scraping purposes to pull the data out of HTML and XML files. It provides a jQuery-like syntax for querying and manipulating HTML documents.
```

[List of NGO Directories](https://docs.google.com/spreadsheets/d/1Op1zqAMotvDs2e4zHPVHkri0gckNuUXizv_blo1Pcyw/edit?usp=sharing)

[List of DaanMatch Web-scraping scripts](https://github.com/DaanMatch/webscrape)
