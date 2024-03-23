# Webscraping-RealEstateFunds

This project involves the development of a web scraping tool designed specifically to extract financial
data from the Investidor 10 website. Investidor 10 is a renowned online platform that provides comprehensive
information on various financial instruments, including stocks, bonds, and other investment opportunities. 
The primary objective of this tool is to automate the collection of vital financial data, which can significantly
enhance investment decision-making processes. By efficiently gathering and processing data from Investidor 10,
the tool aims to offer users timely and accurate financial insights, thereby supporting better investment strategies.
This project not only showcases technical prowess in web scraping techniques but also underscores a practical application
in the financial sector, offering valuable resources for investors seeking informed decisions in their investment ventures.

This Python script is a sophisticated web scraping tool designed to extract specific financial data from the Investidor 10 website, focusing primarily on Real Estate Investment Trusts (REITs) listed in Brazil. Here's a breakdown of its key components and functionalities:

1. **Imports and Setup**: The script begins by importing necessary libraries—`requests` for HTTP requests, `BeautifulSoup` from `bs4` for parsing HTML content, `pandas` for data manipulation, `datetime` for timestamping data collections, and `pytz` for timezone adjustments. It sets the timezone to São Paulo, Brazil, to ensure timestamps align with the local time of the market being analyzed.

2. **Configuration**: It defines the base URL for Investidor 10's section on Financial Investment Funds (FIIs), alongside a user-agent header to mimic browser requests, ensuring access to the site. A list of `tickers` specifies the REITs of interest.

3. **Data Extraction Function**: The `get_fund_data` function is crafted to request and parse data from individual FII pages on the Investidor 10 website. It fetches details like the ticker name, price, price-to-book ratio (P/VP), dividend yield over the last 12 months, and the latest return, capturing these metrics at the current São Paulo time. The extraction process relies on CSS selectors to pinpoint data locations within the HTML structure.

4. **Data Collection Loop**: Through a loop, the script iterates over each ticker in the predefined list, calling `get_fund_data` to collect and append the financial data of each FII to a list. It handles exceptions gracefully, reporting any tickers for which data couldn't be fetched.

5. **Data Processing**: Post-collection, the script utilizes `pandas` to organize the data into a DataFrame for better handling and analysis. It includes a custom function `get_price` to convert price strings into float values, enabling numerical sorting of the FIIs by their price.

6. **DataFrame Operations**: After converting price information into sortable numeric values, the script sorts the DataFrame by price in ascending order and resets the index for clarity, making the dataset ready for analysis or export.

The script exemplifies a practical application of web scraping, data manipulation, and time zone management in Python, tailored for financial analysts and investors interested in the Brazilian REIT market. It automates the retrieval of crucial investment data, facilitating informed decision-making through up-to-date financial metrics.
