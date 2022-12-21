# Stocks Web Application
An Angular web application for virtual stock trading.

## Large Screen Demo
[App Demo large screen](./other/demo-lg.gif)

## Small Screen Demo
[App Demo small](./other/demo-sm.gif)

## Summary
This Angular app provides a platform for stocks trading, including, features such as searching company stock details, buying/selling stocks, keeping track of stock porfolio/watchlist, viewing stock price charts and news, allowing sharing news on twitter and facebook for a given stock, favoriting stocks and tracking their real-time prices with auto-refresh. Express with Nodejs is used as a server proxy for all API calls that uses [Tingo API](https://api.tiingo.com/) for all stock related data, and [News API](https://newsapi.org/) for displaying stock related news. [Highcharts](https://www.highcharts.com/) is used for displaying the chart data for a given ticker.


## Usage
### Running the app Locally:
Before running make sure Angular CLI and Nodejs are installed. For this project ```Angular CLI 10.1.6``` and ```Node 12.19.0``` was used.
1. clone the repo using ```git clone https://github.com/rehmanis/CSCI571-Stocks-Angular.git```
3. ```cd CSCI571-Stocks-Angular```
2. ```npm install```
3. ```ng build```
4. ```npm run devstart```
5. open ```Chrome``` or ```Firefox```. The App can then be started on ```http://localhost:3000/```