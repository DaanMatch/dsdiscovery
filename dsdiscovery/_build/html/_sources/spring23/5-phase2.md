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
