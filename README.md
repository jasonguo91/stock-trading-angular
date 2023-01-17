# Stock Market Web App

Full Stack Stock Market using Angular, Express/Node.js, Bootstrap, Angular Material. 
This Angular app provides a platform for stocks trading, including, features such as searching company stock details, buying/selling stocks, keeping track of stock porfolio/watchlist, viewing stock price charts and news, allowing sharing news on twitter and facebook for a given stock, favoriting stocks and tracking their real-time prices with auto-refresh. Express with Nodejs is used as a server proxy for all API calls that uses [Tingo API](https://api.tiingo.com/) for all stock related data, and [News API](https://newsapi.org/) for displaying stock related news. [Highcharts](https://www.highcharts.com/) is used for displaying the chart data for a given ticker.
The Angular app sends request to Node backend which sends request to 3rd party APIs like Tiingo, NewsAPI and HighStocks API.

## Features of the App

### 1. Autocomplete 
As soon as user begins typing the stock symbol, a list of options with similar prefix appears as shown in the figure below. I used debounceTime function in Angular to set a interval of delay when the user types, after which I send HTTP Get Request to Tiingo API with what the user typed in the search box. The response contains a JSON array of organization names and their ticker values. When the user clicks the buy button, a dialogue appears which allows users add the selected quantity of the stock to their portfolio 

![Autocomplete](https://raw.githubusercontent.com/jasonguo91/stock-trading-angular/main/other/Autocomplete%20.JPG?token=GHSAT0AAAAAAB47OU64PSODBFSYJZDPXC44Y6HD47Q)
![Purchase](https://raw.githubusercontent.com/jasonguo91/stock-trading-angular/main/other/Purchase.JPG?token=GHSAT0AAAAAAB47OU64NOSHUTLAMWEV3XECY6HD5QA)

### 2. Details View - Organization Summary
Once the user clicks on search button from above image, the stock details of that organization are displayed as shown in the image below. These details are updated every 15 seconds when the market is open. If the market is close then the last stock values are displayed. To achieve this, I send GET request to Tiingo API to fetch stock data and HighStock API to get chart data. To get periodic data in 15 second intervals, I used interval function and subscribed to the request.     

![Details Page - Summary](https://raw.githubusercontent.com/jasonguo91/stock-trading-angular/main/other/Details%20Page%20Summary.JPG?token=GHSAT0AAAAAAB47OU65IMYJ73RU5VYXEJPOY6HD6GA)


### 3. Details View - Organization News

As the user clicks the News Tab, he is shown the latest news of the organization as shown in the figure below. I send GET request to NewsAPI to get top 20 latest news. Further if the user clicks on any of the news, a dialogue pops up as shown below and the user can share the news on Twitter and Facebook. He can also view the entire news once he clicks "here"

![Details Page - News](https://raw.githubusercontent.com/jasonguo91/stock-trading-angular/main/other/News%20Share.JPG?token=GHSAT0AAAAAAB47OU642NHBKGHGSBYD6LKMY6HD6SQ)
![News Share](https://raw.githubusercontent.com/jasonguo91/stock-trading-angular/main/other/News%20Share%20-%20Social.JPG?token=GHSAT0AAAAAAB47OU64F5QXP4CEXVFAS2LEY6HD6UA)

### 4. Details View - Organization Yearly Stock Summary

Once the user clicks on the charts tab, I send GET Request to HighStock API and Tiingo API to get the stock details like Open Price, Low Price, High Price, Close Price and Volume past 4 years as shown in figure below. The user can filter this view by months (1,3,6), weeks and years

![Details Page - Charts](https://raw.githubusercontent.com/jasonguo91/stock-trading-angular/main/other/Details%20Page%20-%20Charts.JPG?token=GHSAT0AAAAAAB47OU65UMPSULCZRHZGYI7UY6HD7MA)

### 5. Watchlist View
If the user clicks on Watchlist in the navbar or simply types the url, he is shown a list of companies sorted in ascending order by their stock symbol and the corresponding latest stock data. In the details page as shown below, when the user clicks on the star icon, an alert is shown for 5 seconds notifying that the stock has been added to the watchlist. To achive this, I add the companies in the localStorage and make GET requests to the Tiingo API to display the latest data once the user clicks on watchlist component. As shown in figures below, I have also added validation to display whenever there are no stocks present in the watchlist.  

![Watchlist - Full](https://raw.githubusercontent.com/jasonguo91/stock-trading-angular/main/other/Watchlist%20-%20Full.JPG?token=GHSAT0AAAAAAB47OU65EMM5ANT2BZU6HTFYY6HD7WQ)
![Watchlist- Empty](https://raw.githubusercontent.com/jasonguo91/stock-trading-angular/main/other/Watchlist%20-%20Empty.JPG?token=GHSAT0AAAAAAB47OU65DKM62BF5OALM2ZHUY6HD7XQ)
![notification](https://raw.githubusercontent.com/jasonguo91/stock-trading-angular/main/other/notification.JPG?token=GHSAT0AAAAAAB47OU65BN7PBRQ4JQ7UQX74Y6HEAGQ)

### 6. Portfolio View
If the user clicks on the portfolio button in the navbar, he can view the sorted list of companies stock details and the quantity of stocks he purchased. Again for this, as user clicks buy button in the details page, I store the company and the quantity of stock purchased in the localStorage. While displaying, I read the list from localStorage. I also use validation to display appropriate message if the portfolio is empty. In this view, the user can buy or sell stocks in portfolio. When the user clicks on buy button, he sees an alert as shown in the figure below. The same alert appears when the user clicks on sell button.

![Portfolio Page](https://raw.githubusercontent.com/jasonguo91/stock-trading-angular/main/other/Portfolio%20page.JPG?token=GHSAT0AAAAAAB47OU64UL5CFRTRWUKEOEKEY6HEATA)
![buy portfolio](https://raw.githubusercontent.com/jasonguo91/stock-trading-angular/main/other/Portfolio%20page%20-%20buy.JPG?token=GHSAT0AAAAAAB47OU64TG2YLGCWK674K66SY6HEATQ)

