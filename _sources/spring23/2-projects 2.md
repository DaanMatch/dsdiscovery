# Project

To understand the projects we're going to do and choose the one you're interested in, you should first take a look at this webpage. Information is subject to amendments over the semester.

## Web Scraping Indian NGOs Information using GitHub Actions

**Project Description:**

The goal of this project is to create a comprehensive database of Indian NGOs by extracting information from various websites and sources, and automate the web scraping workflow using GitHub Actions. This information will include registration details, contact information, funding sources, and other relevant data. The project will use web scraping techniques and libraries such as Scrapy or Beautiful Soup to extract the data.

**Tasks:**

- Research and identify relevant websites and sources of information for Indian NGOs
- Develop web scraping scripts using Python and web scraping libraries such as Scrapy or Beautiful Soup
- Extract data from websites including registration details, contact information, funding sources and other relevant data
- Clean and process the data, removing duplicates and formatting it in a structured format.
- Store the data in a database such as PostgreSQL
- Create visualizations and reports to understand the data and insights
- Automate the web scraping workflow using [GitHub actions](https://www.swyx.io/github-scraping), which will run the web scraping scripts, process and save the data, and update the database.

**Technologies:**

- Python
- Web scraping libraries (Scrapy, Beautiful Soup)
- SQL
- PostgreSQL or other database management systems
- GitHub Actions

**Expected Outcomes:**

- A comprehensive database of Indian NGOs that includes registration details, contact information, funding sources and other relevant data
- Data visualization and reports that provide insights into the Indian NGO sector.
- A library of web scraping scripts that can be used for future data collection and updates
- A fully automated web scraping workflow using GitHub Actions, that will allow for regular updates and maintenance of the database.

Note: The project description is a general guidance, and the specific tasks, technologies and outcomes may vary depending on the scope of the project and the data availability. Additionally, web scraping can be against the website's term of service, it's important to check the website's policy and also use the scraping tools in a responsible way.

When learning Python web scraping, you will gain knowledge and skills in the following areas:

1. HTML and CSS: Web scraping involves extracting data from websites, which are written in HTML and CSS. Understanding the structure and elements of HTML and CSS is crucial for being able to locate and extract the desired data from a webpage.
2. HTTP and web protocols: Web scraping requires making HTTP requests to a website and understanding the web protocols such as GET, POST and handling cookies and sessions.
3. XPath and CSS selectors: To extract data from a webpage, you'll need to be able to locate the relevant elements on the page. This can be done using XPath and CSS selectors, which are used to navigate and select elements in an HTML or XML document.
4. Web scraping libraries: Python offers a variety of libraries for web scraping such as Scrapy, Beautiful Soup, Selenium among others, you will learn how to use them to extract data from websites in a fast and efficient way.
5. Data processing and data structures: After extracting data from a website, you will need to process and structure the data. This may involve cleaning, normalizing and transforming the data so it can be used for further analysis.
6. Web scraping best practices: Web scraping can be against the website's term of service and can also cause issues on the website's performance, so it's important to learn about best practices like respecting robots.txt, using APIs when possible and being mindful of the scraping frequency.
7. Ethics and legal considerations: Web scraping can raise legal and ethical issues, it's important to learn the legal framework and ethical considerations around web scraping.

By learning Python web scraping, you will gain the skills and knowledge needed to extract data from websites and use it to drive business decisions, research, and more.

```{dropdown} Webscraping libraries
- **Scrapy:** It is an open-source and collaborative web crawling framework for Python. Scrapy allows you to extract data from websites using spiders, which are scripts that navigate through a website and extract the desired information. Scrapy also provides a built-in way to follow links, handle cookies and sessions, and handle pagination, making it a powerful tool for web scraping.
- **Beautiful Soup:** This is a Python library that allows you to parse HTML and XML documents, and extract data from them. Beautiful Soup is not as robust as Scrapy in terms of handling sessions and pagination but it is simpler to use and is good for small web scraping projects, it's also helpful when you want to extract data from a single page.
Both libraries are free and open-source, and have an active community that provides support and tutorials.

It's worth noting that web scraping can be against the website's term of service and can also cause issues on the website's performance, it's important to check the website's policy and also use the scraping tools in a responsible way.
```

```{dropdown} [NGO Directory](https://docs.google.com/spreadsheets/d/1Op1zqAMotvDs2e4zHPVHkri0gckNuUXizv_blo1Pcyw/edit#gid=0)
- https://ngodarpan.gov.in/index.php/home/statewise
- https://ngosindia.com/ngos-of-india/
- https://give.do/discover/
- https://www.indiangoslist.com
- https://www.fueladream.com/categories/charity
- https://www.globalgiving.org/search/?size=25&nextPage=1&sortField=sortorder&selectedLocations=00india&loadAllResults=true
- https://www.ketto.org/crowdfunding/fundraisers?query=Ngo
```

## Testing for Broken links

- Verify the links: First, you will need to verify the links to ensure that they are valid and functional. This can be done by making HTTP requests to each URL and checking the response code. If the response code is in the 200-299 range, it indicates a successful connection, and the link is working. If the response code is in the 400-599 range, it indicates an error, and the link may be broken.
- Logging: Next, you should log the results of your link verification process. This log should include the URL, the response code, and a timestamp. This will allow you to keep track of the links that are working and those that are not, and to easily identify any changes over time.
- Testing: You should also set up a process for regularly testing the links to ensure that they remain valid. This can be done using a script that runs at a specified interval and checks the links in your log. If any links are found to be broken, you should be notified so that you can take action.
- Reporting: Finally, it's important to have a reporting mechanism in place so that you can quickly see the status of all the links and identify any issues. This could be as simple as a spreadsheet or a dashboard that shows the status of each link over time.
